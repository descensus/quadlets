# Setup process on RHEL-ish system

dnf install podman systemd-container
useradd -m _serviceaccount
loginctl enable-linger _serviceaccount
machinectl shell --uid=_serviceaccount

Place the containerfile in .config/containers/systemd
systemctl --user enable --now myservice
