To learn Kubernetes we need to first learn what is Containers and Orchestration
# Containers
- Containers are used in computing to package and run software applications along with their dependencies and settings.
- They offer a way to isolate applications from the environment they run in, providing consistency across different computing environments and making it easier to deploy, manage, and scale applications.
- Example:
  - consider your computer or server as a workshop where you want to run multiple applications. Each application might need different versions of programming languages, libraries, or configurations, just like each task in your workshop might require a specific set of tools from your toolbox.
  - Here's where containers come in—they're like individual toolboxes for each specific task. You can neatly pack each application along with all the tools it needs (dependencies, libraries, configurations) into its own container.
  - This way, each application operates independently without interfering with others, just like how each task in your workshop has its own set of tools, and they don't mix up or get in the way of each other.

# Container vs Virutal Machine
| VM       | Container |
| -------- | ------- |
| VMs emulate a physical computer and run on a hypervisor, which is software that creates and manages VMs.  | Containers virtualize the operating system, not the hardware. They share the host system's kernel but isolate the application's environment.|
| Each VM includes a guest operating system, application, necessary binaries, and libraries. It creates a full virtualized environment. | Containers package an application and its dependencies into a single unit, providing an isolated environment for running the application.|
| VMs are resource-intensive because they require a separate operating system for each instance.| They are lightweight, as they don't need a separate operating system for each container. Instead, they share the host OS's kernel, making them faster to start and more resource-efficient than VMs |

# Orchestration 
- Container orchestration refers to the automated management and coordination of multiple containers to ensure they run efficiently, reliably, and at scale within an environment.
- It involves tasks like deployment, scaling, networking, and resource allocation across containerized applications.
- ![image](https://github.com/itsarkcodes/Mastering-DevOps/assets/87442305/1e48b597-f346-4b4b-8be3-0d654d534223)


