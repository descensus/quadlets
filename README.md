# Setup process for rootless podman quadlets on RHEL-ish system


> dnf install podman systemd-container
> 
>useradd -m _serviceaccount
> 
>loginctl enable-linger _serviceaccount
> 
>machinectl shell --uid=_serviceaccount
>
> mkdir -p ~/.config/containers/systemd
>
>  \# Place the containerfile in .config/containers/systemd/
>
>systemctl --user daemon-reload
> 
>  systemctl --user enable --now myservice



