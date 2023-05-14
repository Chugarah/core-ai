# Nx Mono Repo Installation

The Nx tool offers two approaches to monorepo development: Integrated Monorepo and Packaged-based Monorepo. The differences between these two approaches are as follows:

Integrated Monorepo

In an Integrated Monorepo, all the code exists in a single repository, and all the projects share the same node_modules folder.
Code can be shared between different projects by importing it directly from the file system.
Integrated Monorepos are more straightforward to set up and require less configuration than Packaged-based Monorepos.
However, Integrated Monorepos can be more difficult to scale as the number of projects and shared code increases.
Integrated Monorepos are ideal for small to medium-sized projects with a limited number of shared dependencies.
Packaged-based Monorepo

In a Packaged-based Monorepo, each project is a separate package with its own node_modules folder.
Code is shared between projects using package dependencies, which can be versioned and published to an internal registry.
Packaged-based Monorepos are more scalable than Integrated Monorepos and are better suited for large projects with many shared dependencies.
However, Packaged-based Monorepos can be more difficult to set up and require more configuration than Integrated Monorepos.

## Windows Setup

We will install PNPM globally, and then use PNPM to install the Nx CLI.

### 1. Install PNPM

```powershell
iwr https://get.pnpm.io/install.ps1 -useb | iex
```

### 2. Install Conda

Install Conda and create environment

```powershell
# Download Miniconda
iwr https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe -OutFile Miniconda3-latest-Windows-x86_64.exe

# Install Miniconda
.\Miniconda3-latest-Windows-x86_64.exe /InstallationType=JustMe /AddToPath=1 /RegisterPython=0 /S /D=C:\Miniconda3

# Activate Conda
conda init powershell
```

Create Env

```powershell
# Create Conda Env
conda create -n conda activate core-ai-repo -y 
```

Activate Conda Env

```powershell
# Activate Conda Env
conda activate core-ai-repo
```

### 3. Install NodeJS

```powershell
# Install NodeJS
conda install -c conda-forge nodejs -y
```

### 2. Creating NX Workspace

```powershell
# Install Nx CLI
npx create-nx-workspace@latest core-ai --preset=npm
pnpm install -g nx
```
