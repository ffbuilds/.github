# .github

Hosts the profile and shared workflows for ffbuilds.

## Shared workflows

- `bump.yml` — daily version PRs via [wader/bump](https://github.com/wader/bump), then `gh pr merge --auto --squash`
- `docker.yml` — Alpine 3.24.1 + edge matrix, GHCR publish, GitHub Releases, FFmpeg cascade rebuilds
- `linter.yml` — super-linter

Callers must pass `push_images` so images are published on `main` (reusable workflows see `github.event_name` as `workflow_call`).

## Org wiring

New library images live in this workspace as `static-lib{lcms2,jxl,srt,ssh,zmq,rabbitmq,rtmp,vvenc,xeve,xevd}`. Create and push them with:

```sh
for lib in lcms2 jxl srt ssh zmq rabbitmq rtmp vvenc xeve xevd; do
  gh repo create "ffbuilds/static-lib${lib}" --public \
    --source="/Users/barrett/github.com/ffbuilds/static-lib${lib}" \
    --remote=origin --push
done
```

Enable auto-merge so green bump PRs land:

```sh
gh repo list ffbuilds --limit 200 --json name -q '.[].name' | while read -r name; do
  gh api -X PATCH "repos/ffbuilds/${name}" -f allow_auto_merge=true
done
```

Require CI before merge (check name `docker / ci-success`):

```sh
gh repo list ffbuilds --limit 200 --json name -q '.[].name' | while read -r name; do
  gh api -X PUT "repos/ffbuilds/${name}/branches/main/protection" \
    --input - <<'EOF'
{
  "required_status_checks": {
    "strict": true,
    "contexts": ["docker / ci-success"]
  },
  "enforce_admins": false,
  "required_pull_request_reviews": null,
  "restrictions": null
}
EOF
done
```

Publish `.github` reusable workflows to `main` before the first FFmpeg 9 image build. New lib images must exist in GHCR before `static-ffmpeg-gplv3` can `COPY --from` them.
