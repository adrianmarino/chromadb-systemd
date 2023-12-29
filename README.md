# [Chroma](https://www.trychroma.com/) database systemd

* Install chtoma database as systemd daemon. 
* Run daemon with your regular user.

## Requirements

* Linux
* miniconda
* chromadb


## Setup

**Step 1**: Clone repo. 

```bash
$ cd ~
$ git clone https://github.com/adrianmarino/chromadb-systemd.git
$ mv chromadb-systemd chromadb
$ cd chromadb
```

**Step 2**: Create conda environment required to run chromadb.

```bash
$ conda env update -f environment.yml
```

**Step 3**: Copy service file user level systemd config path:

```bash
$ cp chromadb.service ~/.config/systemd/user/
```

**Step 4**: Refresh systemd daemon with updated config.

```bash
$ systemctl --user daemon-reload
```

**Step 5**: Start service on boot.

```bash
$ systemctl --user enable chromadb
```

**Step 6**: Start chromadb as systemd daemon.

```bash
$ systemctl --user start chromadb
```

## Config file

`config.conf`:
```bash
CONDA_PATH="/opt/miniconda3"
ENV="chromadb"
PORT="9090"
HOST="0.0.0.0"
```
