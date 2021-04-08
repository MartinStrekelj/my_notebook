# SSH (secure shell)

## Basics

:::note

SSH is a protocol. Other protocols are HTTP, SFTP, FTP...

With SSH you can share files and control remote computers/servers.

SSH is terminal based.

~~Windows OS usually needs a client to access ssh~~ Now is build-in to powershell.

:::

Most common use cases:

- Access remote computer.
- Github
- Access to the remote server / production environment.

## Common SSH commands

Template:

```bash
ssh {user}@{host}
```

Example:

```bash
ssh root@192.168.1.1
```

To exit SSH session:

```bash
exit
```

## How SSH work

- **Symetrical encryption**
  - ["Public Key Cryptography - Computerphile"](https://www.youtube.com/watch?v=GSIDS_lvRv4)
  - ["Secret Key Exchange (Diffie-Hellman) - Computerphile"](https://www.youtube.com/watch?v=NmM9HA2MQGI)

- **Asymetrical encryption**
  - ["Asymmetric Encryption - Simply explained"](https://www.youtube.com/watch?v=AQDCe585Lnc)

- **Hashing**

    One way hashing:
  - ["SHA: Secure Hashing Algorithm - Computerphile"](https://www.youtube.com/watch?v=DMtFhACPnTY)
  - `plaintext` -> `hash`
  - ~~`hash` -> `plaintext`~~

- **Authentication**
  - Passwords
  - SSH Auth *(main reason for SSH with Github)*

## SSH Authentication

Check for `.ssh` folder. `ls -a` to show hidden folders.
Cd to `~./.ssh`.
Alternatively if it does not exist create a new hidden folder in root directory named `.ssh`.

Create a public/private keygen:

```bash
ssh-keygen -C "<email_address>"
```

You will be prompted: (you can leave passphrase empty or add it to generate extra layer of security)

```bash
Enter file in which to save the key (~/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

If you have multiple identities you can add new with:

```bash
ssh-add path-to-private-key
```

### To authenticate to specific server

Copy public key `id_rsa.pub` (you can use `pbcopy`) to server `authorized_keys` (open with `nano` or `vim`) file inside `~/.ssh` folder (on server).

## Extras

`Rsync`: [Rsync](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)

`Digital ocean`: [DigitalOcean](https://www.digitalocean.com/)

`pbcopy`: [pbcopy](https://garywoodfine.com/use-pbcopy-on-ubuntu/)
