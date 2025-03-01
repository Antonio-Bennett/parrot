# 🦜
A hassle-free, highly performant and fast evolving Discord music bot built with Serenity in Rust.

## Deployment

### Usage
Just [create a bot account](https://github.com/aquelemiguel/parrot/wiki/Create-Your-Discord-Bot), copy its token into the `DISCORD_TOKEN` environment variable within `.env`.

### Docker

For the hassle free deployment:

```shell
docker run -d --env-file .env ghcr.io/aquelemiguel/parrot:latest
```

## Development

Make sure you've installed Rust. You can install Rust and its package manager, `cargo` by following the instructions on https://rustup.rs/.
After installing the requirements below, simply run `cargo run`.

### Linux / MacOS
The command below installs a C compiler, GNU autotools, Opus (Discord's audio codec), youtube-dl, FFmpeg and the SSL library for development.


```shell
apt install build-essential autoconf automake libtool m4 libopus-dev youtube-dl ffmpeg libssl-dev
```

### Windows

If you are using the MSVC toolchain, a prebuilt DLL for Opus is already provided for you.  
You will only need to download [FFmpeg](https://ffmpeg.org/download.html), and install youtube-dl which can be done through Python's package manager, pip.
```shell
pip install youtube_dl
```

If you are using Windows Subsystem for Linux (WSL), you should follow the [Linux/MacOS](#linux--macos) guide, and, in addition to the other required packages, install pkg-config, which you may do by running:

```shell
apt install pkg-config
```

## Testing

Tests are available inside the `src/tests` folder. They can be ran via `cargo test`. It's recommended that you run the tests before submitting your Pull Request.
Increasing the test coverage is also welcome.

### Docker

Within the project folder, simply run the following:

```shell
docker build -t parrot .
docker run -d --env-file .env parrot
```
