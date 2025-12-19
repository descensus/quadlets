# Setup process example for rootless podman quadlets on RHEL-ish system


    dnf install -y podman systemd-container
    useradd -m _serviceaccount
    loginctl enable-linger _serviceaccount
    machinectl shell --uid=_serviceaccount
    mkdir -p ~/.config/containers/systemd
    # Place the containerfile of choice in .config/containers/systemd/
    systemctl --user daemon-reload
    systemctl --user start myservice

    # Do we have any container running?
    podman ps
    podman ps -a

    # troubleshoot with 
    journalctl --no-pager
