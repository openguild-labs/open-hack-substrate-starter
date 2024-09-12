# OpenHack Workshop - Substrate Starter

![Substrate_Starter](https://github.com/openguild-labs/open-hack-substrate-starter/assets/56880684/99d80d93-082e-4b17-9cc5-817c33d7cab0)

Repositoriy is made by the **OpenGuild Labs** to introduce OpenHack workshop participants about Polkadot SDK - Substrate and help the participants to get familiar with the blockchain builder tool.

## Participant Registration

Add your information to the below list to officially participate in the workshop challenge (This is the first mission of the whole workshop)

| Emoji | Name               | Github Username                                   | Occupations                 |
| ----- | ------------------ | ------------------------------------------------- | --------------------------- |
| 💻    | Tin Chung          | [chungquantin](https://github.com/chungquantin)   | DevRel Lead Polkadot SEA    |
| 💻    | Yang               | khoahua04                                         | Dev @ Nexm Labs             |
| 💻    | Quoc Tran          | quoctran1                                         | Dev                         |
| 🛀    | Dam Nguyen         | [damnt055](https://github.com/DamNT055)           | Amateur Coding at Mia       |
| 🦀    | Trong Dinh         | trongdth                                          | Ninja @ Nexm Labs           |
| 💻:3  | Anh Pham           | [FucktheKingcode](https://github.com/FucktheKingcode) | Dev to the Moon         |
| 🦀    | Khuong Duy         | [marciohardcore](https://github.com/marciohardcore) | Student                     |
| 🦀    | Phong Cao          | [katafo](https://github.com/katafo)               | Backend Dev                 |
| 🦀    | Phu Sy             | [phusy2001](https://github.com/phusy2001)         | Developer                   |
| 🦀    | Leo Pham           | [HongThaiPham](https://github.com/HongThaiPham)   | Blockchain Dev              |
| 💻    | Armielyn Obinguar  | [armlynobinguar](https://github.com/armlynobinguar) | DevRel @ Virtuals Protocol  |

## Learn more about OpenGuild

- **About us:** [Learn more about us](https://openguild.wtf/about)
- **Website:** [OpenGuild Website](https://openguild.wtf/)
- **Github:** [OpenGuild Labs](https://github.com/openguild-labs)
- **Discord**: [Openguild Discord Channel](https://discord.gg/bcjMzxqtD7)

## Goals of the workshop

1. Get familiar with Git & Github via open-source contribution
   - Install `git` on your local device
   - Git `fork` and `clone` command
   - `commit` and `push` code from your local device to Github
   - Create a `Pull Request` and merge with this repository
2. Install and setup Rust on your local device
3. Install and setup `pop-cli` on your local device
4. Create a EVM-compatible parachain with `pop-cli`

---

## Mission 1: Get familiar with Git & Github via open-source contribution

- Step 1: Install Git & Github Desktop (optional) on your local device
- Step 2: Fork this repository by click the `Fork button` on Github

![image](https://github.com/openguild-labs/open-hack-rust-starter/assets/56880684/7fa2f01a-b523-4208-92db-d8af7a274d98)

<img width="683" alt="Screenshot 2024-04-19 at 16 20 00" src="https://github.com/openguild-labs/open-hack-rust-starter/assets/56880684/138d1d07-5c0f-4fc3-b73d-8eafae3c692d">

- Step 3: `Clone` the forked repository to your local device using the below command

```
git clone https://github.com/[name-of-your-account]/open-hack-rust-starter.git
```

Replace the `[name-of-your-account]` with your Github username. For example, if my username is `chungquantin`, I would do the below command to clone the repository to my local device.

```
git clone https://github.com/chungquantin/open-hack-rust-starter.git
```

- Step 4: Edit the `README.md` file to register for official participation

Go to **Participant Registration** section and register to be the workshop participants. Add the below to the list, replace any placeholder with your personal information.

```
| 🦀    | Your Name | Your Github username | Your current occupation |
```

- Step 5: `Commit` your code and push to the forked Github repository

````
git add .
git commit -m "Register for OpenHack workshop"
```

- Step 6: Create a `Pull Request` to merge your changes to this repository and name your PR as `Your name | Register for OpenHack workshop`

<img width="1166" alt="Screenshot 2024-04-19 at 16 23 45" src="https://github.com/openguild-labs/open-hack-rust-starter/assets/56880684/7554ca7d-da68-4a23-893a-4f2c11a78d37">

---

## Mission 2: Install and setup Rust on your local device

The first step is to install Rust. We’ll download Rust through `rustup`, a
command line tool for managing Rust versions and associated tools. You’ll need
an internet connection for the download.

> Note: If you prefer not to use `rustup` for some reason, please see the
> [Other Rust Installation Methods page][otherinstall] for more options.

The following steps install the latest stable version of the Rust compiler.

### Installing `rustup` on Linux or macOS

If you’re using Linux or macOS, open a terminal and enter the following command:

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
````

The command downloads a script and starts the installation of the `rustup`
tool, which installs the latest stable version of Rust. You might be prompted
for your password. If the install is successful, the following line will appear:

```text
Rust is installed now. Great!
```

You will also need a _linker_, which is a program that Rust uses to join its
compiled outputs into one file. It is likely you already have one. If you get
linker errors, you should install a C compiler, which will typically include a
linker. A C compiler is also useful because some common Rust packages depend on
C code and will need a C compiler.

On macOS, you can get a C compiler by running:

```console
$ xcode-select --install
```

Linux users should generally install GCC or Clang, according to their
distribution’s documentation. For example, if you use Ubuntu, you can install
the `build-essential` package.

### Installing `rustup` on Windows

On Windows, go to [https://www.rust-lang.org/tools/install][install] and follow
the instructions for installing Rust. At some point in the installation, you’ll
be prompted to install Visual Studio. This provides a linker and the native
libraries needed to compile programs. If you need more help with this step, see
[https://rust-lang.github.io/rustup/installation/windows-msvc.html][msvc]

### Troubleshooting

To check whether you have Rust installed correctly, open a shell and enter this
line:

```console
$ rustc --version
```

You should see the version number, commit hash, and commit date for the latest
stable version that has been released, in the following format:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

If you see this information, you have installed Rust successfully! If you don’t
see this information, check that Rust is in your `%PATH%` system variable as
follows.

In Windows CMD, use:

```console
> echo %PATH%
```

In PowerShell, use:

```powershell
> echo $env:Path
```

In Linux and macOS, use:

```console
$ echo $PATH
```

If that’s all correct and Rust still isn’t working, there are a number of
places you can get help. Find out how to get in touch with other Rustaceans (a
silly nickname we call ourselves) on [the community page][community].

### Updating and Uninstalling

Once Rust is installed via `rustup`, updating to a newly released version is
easy. From your shell, run the following update script:

```console
$ rustup update
```

To uninstall Rust and `rustup`, run the following uninstall script from your
shell:

```console
$ rustup self uninstall
```

---

## Mision 3: Install `pop-cli`

Detailed guidelines can be found here [Learn more about POP Cli](https://github.com/r0gue-io/pop-cli)

---

## Mision 4: Create a EVM-compatible parachain

```
# Create a minimal parachain
pop new parachain my-app

# Create a evm parachain
pop new parachain my-app pop -t evm

# Run the below command to boot your local relaychain
pop up parachain -f ./network.toml
```

If your parachain can be run successfully then you already finished the exercise. Submit to OpenGuild Community to claim 100XP. [Learn how to claim the XP and Bounty](https://handbook.openguild.wtf/general-information/membership/how-to-claim-xp-and-bounty).

After finish the challenge, push your code to your personal repository named `og-parachain-built-with-pop`

---

## Mission 5 (Optional): Advanced Pallet configuration

- Bounty: 2 DOT for every 3 fastest challengers

[Add a nickname customization functionality with pallet-nicks](https://docs.substrate.io/tutorials/build-application-logic/add-a-pallet/)

After finish the challenge, push your code to your personal repository named `og-parachain-built-with-pop`

# 🙌 How to contribute to the community?

To submit a proposal, ideas, or any questions, please submit them here: [OpenGuild Discussion 💬](https://github.com/orgs/openguild-labs/discussions)
View tickets and activities that you can contribute: [Community Activities 🖐️](https://github.com/orgs/openguild-labs/discussions/categories/activities)

- **Help to grow the community:** Community growth is a collective effort. By actively engaging with and inviting fellow enthusiasts to join our community, you play a crucial role in expanding our network. Encourage discussions, share valuable insights, and foster a welcoming environment for newcomers.

- **Participate in workshops and events:** Be an active participant in our workshops and events. These sessions serve as valuable opportunities to learn, collaborate, and stay updated on the latest developments in the Polkadot ecosystem. Through participation, you not only enhance your knowledge but also contribute to the collaborative spirit of OpenGuild. Share your experiences, ask questions, and forge connections with like-minded individuals.

- **Propose project ideas:** Your creativity and innovation are welcomed at OpenGuild. Propose project ideas that align with the goals of our community. Whether it's a new application, a tool, or a solution addressing a specific challenge in the Polkadot ecosystem, your ideas can spark exciting collaborations.

- **Contribute to our developer tools:** Get involved in the ongoing development and improvement of tools that aid developers in their projects. Whether it's through code contributions, bug reports, or feature suggestions, your involvement in enhancing these tools strengthens the foundation for innovation within OpenGuild and the broader Polkadot community.
