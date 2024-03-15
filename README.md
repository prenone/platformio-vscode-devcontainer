# **PlatformIO Development Container** for Visual Studio Code (Community)

## Summary

*Develop with PlatformIO. Includes all needed SDKs, extensions, and dependencies, and autonomously handle connected hardware.*

| Metadata                    | Value                          |
| --------------------------- | -------------------------------|
| *Contributors*              | [On Github](https://github.com/prenone/platformio-vscode-devcontainer/graphs/contributors)    |
| *Categories*                | IoT                            |
| *Definition type*           | Dockerfile                     |
| *Container host OS support* | Linux, macOS (not tested),     |
| *Container OS*              | Debian (`bookworm`, `bullseye`)|
| *Languages, platforms*      | PlatformIO, C++, Python        |

## Using this definition

This definition should work unmodified. It does not require adjustments on the host platform (i.e. no need to adjust udev rules or a user's groups)

### Accessing the microcontrollers from the container

The container binds to `/dev/` and has direct access to devices connected through the host platform. It manages its own udev rules and permissions indipendently from the host OS.

This feature usually works on debian-based distributions. However, some distros like Fedora use different group IDs.
If your distro's dialout (or equivalent) group id is not `20`, you need to set the `FEDORA_COMPAT` arg to `"1"`

### Variants

This devcontainer supports the `debian` base images as variants, as follows:

| Debian release | `VARIANT` value           |
| ---------------| --------------------------|
| Debian 12      | `bookworm` or `debian-12` |
| Debian 11      | `bullseye` or `debian-11` |
| Debian 10      | `buster` or `debian-10`   |

> [!TIP]
> If you are setting up a new project, avoid debian 10 (`buster`) as it will become EOL on 2024-06-30.
> Use `bookworm` as it is an LTS that will be supported until 2028.

> [!NOTE]
> Nothing is inherently inompatible with the `ubuntu` base images AFAIK, however they were not tested.

## Adding the definition to your folder

1. If this is your first time using a development container, please see getting started information on [setting up](https://aka.ms/vscode-remote/containers/getting-started) Remote-Containers.
2. Clone this repository locally.
3. Start VS Code and open your project folder.
4. Use your local operating system's file explorer to drag-and-drop the locally cloned copy of the `.devcontainer` folder for this definition into the VS Code file explorer for your opened project.

After following these steps the contents of the `.devcontainer` folder in your project can be adapted to meet your needs.

1. Finally open the **Command Palette** and run **Remote-Containers: Reopen Folder in Container** to start using the definition.

## Notes

This container runs in `--privileged` mode.
