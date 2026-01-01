# Setup process example for rootless podman quadlets on RHEL-ish system

    SVC="_serviceaccount"
    dnf install -y podman systemd-container
    useradd -m $SVC
    loginctl enable-linger $SVC
    machinectl shell --uid=$SVC
    mkdir -p ~/.config/containers/systemd
    # Place the containerfile of choice in .config/containers/systemd/
    systemctl --user daemon-reload
    systemctl --user start myservice

    # Do we have any container running?
    podman ps
    podman ps -a

    # troubleshoot with 
    journalctl --no-pager
