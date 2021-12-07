# **PlatformIO Development Container** for Visual Studio Code (Community)

## Summary

*Develop with PlatformIO. Includes all needed SDKs, extensions, and dependencies, and autonomously handle connected hardware.*

| Metadata                    | Value                       |
| --------------------------- | --------------------------- |
| *Contributors*              | Achille Merendino (prenone) |
| *Categories*                | IoT                         |
| *Definition type*           | Dockerfile                  |
| *Container host OS support* | Linux, macOS (not tested),  |
| *Container OS*              | Ubuntu                      |
| *Languages, platforms*      | PlatformIO, C++, Python     |

## Using this definition

This definition should work unmodified. It does not require adjustments on the host platform (i.e. no need to adjust udev rules or a user's groups)

The container binds to `/dev/` and has direct access to devices connected through the host platform. It manages its own udev rules and permissions indipendently from the host OS.

### Adding the definition to your folder

1. If this is your first time using a development container, please see getting started information on [setting up](https://aka.ms/vscode-remote/containers/getting-started) Remote-Containers.
2. Clone this repository locally.
3. Start VS Code and open your project folder.
4. Use your local operating system's file explorer to drag-and-drop the locally cloned copy of the `.devcontainer` folder for this definition into the VS Code file explorer for your opened project.

After following these steps the contents of the `.devcontainer` folder in your project can be adapted to meet your needs.

1. Finally open the **Command Palette** and run **Remote-Containers: Reopen Folder in Container** to start using the definition.

## Notes

This container runs in `--privileged` mode.
