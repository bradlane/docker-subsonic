# docker-subsonic

A minimal [Alpine Linux](http://alpinelinux.org/)-based multi-arch [Subsonic](http://www.subsonic.org/) image.
Based on [stanvit/subsonic](https://hub.docker.com/r/stanvit/subsonic)

## Container configuration

The following environment variables could be used:

  * SUBSONIC_USERID - the default UID to run the server (default 1000)
  * SUBSONIC_PORT - TCP port to bind to (default 4040)
  * SUBSONIC_HOME - the direcotry for Subsonic settings and log (default /subsonic/home)
  * SUBSONIC_MUSIC_FOLDER - default music folder (default /subsonic/music)
  * SUBSONIC_PODCAST_FOLDER - default podcast folder (default /subsonic/podcasts)
  * SUBSONIC_PLAYLIST_FOLDER - default playlist folder (default /subsonic/playlists)
  * SUBSONIC_CONTEXT_PATH - subsonic HTTP context path (default /)
  * SUBSONIC_MAX_MEMORY - Java heap memory, MB (default 150)

The following volumes are created by default:

  * /subsonic/home
  * /subsonic/music
  * /subsonic/podcasts
  * /subsonic/playlists

## Running the container

    docker run -d --name=subsonic \
    -p 4040:4040 \
    -v ~/subsonic/home:/subsonic/home \
    -v ~/media/Music:/subsonic/music \
    -v ~/media/Podcasts:/subsonic/podcasts \
    -v ~/media/Music/playlists:/subsonic/playlists \
    -e SUBSONIC_USERID=1004 \
    lanehq/subsonic
