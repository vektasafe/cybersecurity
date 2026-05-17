# Magikarp Ground Mission

**Category:** General Skills
**Difficulty:** Easy
**Author:** syreal

---

## Challenge

SSH into a remote server and navigate between directories to find three parts of a flag.
ssh ctf-player@wily-courier.picoctf.net -p 55070
Password: 8c606eb
---

## Solution

**Step 1 -- Connect via SSH**

```bash
ssh ctf-player@wily-courier.picoctf.net -p 55070
```

Enter the password when prompted.

**Step 2 -- List and read files in the home directory**

```bash
ls
cat 1of3.flag.txt
cat instructions-to-2of3.txt
```

Output:
- `1of3.flag.txt` contains: `picoCTF{xxsh_`
- `instructions-to-2of3.txt` says: go to `/`

**Step 3 -- Navigate to root and read the second part**

```bash
cd /
cat 2of3.flag.txt
cat instructions-to-3of3.txt
```

Output:
- `2of3.flag.txt` contains: `0ut_0f_//4t3r_`
- `instructions-to-3of3.txt` says: go home `~`

**Step 4 -- Navigate home and read the third part**

```bash
cd ~
cat 3of3.flag.txt
```

Output:
- `3of3.flag.txt` contains: `0b24fc4f}`

---

## Flag

`picoCTF{xxsh_0ut_0f_//4t3r_0b24fc4f}`

---

## Key Takeaways

- `cd /` navigates to the root of the filesystem
- `cd ~` navigates to the current user's home directory
- `ls` lists files in the current directory
- `cat` reads file contents
- Flags are sometimes split across multiple files and directories
