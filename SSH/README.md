# Membuat SSH Key baru dan menambahkan ke ssh-agent

## Generate SSH KEY
Penjelasan lebih lengkat tentang apa itu SSH dapat dilihat [disini](https://www.ssh.com/academy/ssh/keygen#what-is-ssh-keygen?)


## Refrensi : Dokumen tentang SSH Key dari Github 
* [Generating a new SSH Key and adding it to ssh-agent](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
* [Adding a new ssh key to Github account](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)


Langkah 
1. `Open Git Bash`
Ketik kode berikut di Gitbash command ```$ ssh-keygen -t ed25519 -c "email@gmail.com"```
Tekan enter sampai muncul sha 256

| ed25519 adalah algoritma baru yang barusaja ditambahkan di OpenSSH. Dukungan algoritma ini belum dipakai secara umum. Maka dari itu penggunaan untuk tujuan umum dari aplikasi tidak disarankan.
|-----------|

2. Pastikan ssh-agent berjalan dikomputer kita.
Untuk mengecheck secara manual ketik ```$ eval "$(ssh-agent -s)"```
Untuk auto launching lihat [Refrensi](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/working-with-ssh-key-passphrases)

3. Masukan SSH Private Key ke ssh-agent
Ganti `idKita`dengan nama file dari private key kita
```$ ssh-add ~/.ssh/id_idKita```

# Menambahkan SSH Key baru kedalam Akun Github
1. *Copy* SSH public key ke clipboard
Ganti idKita dengan nama yang sesuai dengan nama file kita yang berada di folder `~/.ssh`.

```$ clip < ~/.ssh/id_idKita.pub
# Copies the contents of the id_idKita.pub file to your clipboard```

2. Masukan key yang sudah dicopy kedalam [Github add new ssh](https://github.com/settings/ssh/new)
3. Akan muncul form untuk memasukan password github.
