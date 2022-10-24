Builds for [FFmpeg](https://ffmpeg.org) and its supporting libraries.

## FFmpeg
- [static-ffmpeg-gplv3](https://github.com/ffbuilds/static-ffmpeg-gplv3) - a static GPL version 3 build
- [static-ffmpeg-minimal](https://github.com/ffbuilds/static-ffmpeg-minimal) - a static minimal FFmpeg build (LGPL)

## Libraries built from source
- [libaom](https://github.com/ffbuilds/static-libaom)
- [libaribb24](https://github.com/ffbuilds/static-libaribb24)
- [libass](https://github.com/ffbuilds/static-libass)
- [libbluray](https://github.com/ffbuilds/static-libbluray)
- [libbrotli](https://github.com/ffbuilds/static-libbrotli)
- [libdav1d](https://github.com/ffbuilds/static-libdav1d)
- [libdavs2](https://github.com/ffbuilds/static-libdavs2)
- [libgme](https://github.com/ffbuilds/static-libgme)
- [libgsm](https://github.com/ffbuilds/static-libgsm)
- [libkvazaar](https://github.com/ffbuilds/static-libkvazaar)
- [libmodplug](https://github.com/ffbuilds/static-libmodplug)
- [libmp3lame](https://github.com/ffbuilds/static-libmp3lame)
- [libmysofa](https://github.com/ffbuilds/static-libmysofa)
- [libogg](https://github.com/ffbuilds/static-libogg)
- [libopencore-amr](https://github.com/ffbuilds/static-libopencore-amr)
- [libopenjpeg](https://github.com/ffbuilds/static-libopenjpeg)
- [libopus](https://github.com/ffbuilds/static-libopus)
- [librav1e](https://github.com/ffbuilds/static-librav1e)
- [librubberband](https://github.com/ffbuilds/static-librubberband)
- [libsamplerate](https://github.com/ffbuilds/static-libsamplerate)
- [libshine](https://github.com/ffbuilds/static-libshine)
- [libspeex](https://github.com/ffbuilds/static-libspeex)
- [libsvtav1](https://github.com/ffbuilds/static-libsvtav1)
- [libtheora](https://github.com/ffbuilds/static-libtheora)
- [libtwolame](https://github.com/ffbuilds/static-libtwolame)
- [libuavs3d](https://github.com/ffbuilds/static-libuavs3d)
- [libvidstab](https://github.com/ffbuilds/static-libvidstab)
- [libvmaf](https://github.com/ffbuilds/static-libvmaf)
- [libvorbis](https://github.com/ffbuilds/static-libvorbis)
- [libvpx](https://github.com/ffbuilds/static-libvpx)
- [libwebp](https://github.com/ffbuilds/static-libwebp)
- [libx264](https://github.com/ffbuilds/static-libx264)
- [libx265](https://github.com/ffbuilds/static-libx265)
- [libxavs2](https://github.com/ffbuilds/static-libxavs2)
- [libxml2](https://github.com/ffbuilds/static-libxml2)
- [libxvid](https://github.com/ffbuilds/static-libxvid)
- [libzimg](https://github.com/ffbuilds/static-libzimg)

## Key Features

### Cross-platform
Runs on amd64, arm64, arm/v7, and arm/v6.

### Matrix Builds
We matrix build on Alpine version and platform. Manifest lists are generated after all of the builds are complete, so that the images can always be referenced by the same tag or digest (instead of one tag/digest per platform).

### Caching
We utilize the [GitHub Actions cache](https://docs.docker.com/build/building/cache/backends/gha/) for docker layer caching with mode=max. For this reason, we try to keep the layers small and fast.

### Storage in GHCR
We store all of the images publicly in ghcr.io.

## Versioning tools
- [wader/bump](https://github.com/wader/bump)
- @dependabot

## Contributors
- [@wader](https://github.com/wader) - orignal author of [wader/static-ffmpeg](https://github.com/wader/static-ffmpeg)
- [@binoculars](https://github.com/binoculars)
