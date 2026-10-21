# Satuk OS packages

Signed pacman repository for [Satuk OS](https://github.com/inilvinilra/SatukOS).
This repository holds built packages only. Packages and the repository database
are served from the `x86_64` release and signed with:

    AF5EAECF63ADA7A1C9166D160C23BE57E953F089
    SatukOS Package Signing Key <packages@satukos.linux>

Satuk OS ships this key (`satukos-keyring`) and the repository entry
(`satukos-mirrorlist`), so an installed system receives updates with
`pacman -Syu`. On another Arch system:

    pacman-key --recv-keys AF5EAECF63ADA7A1C9166D160C23BE57E953F089
    pacman-key --finger AF5EAECF63ADA7A1C9166D160C23BE57E953F089   # compare
    pacman-key --lsign-key AF5EAECF63ADA7A1C9166D160C23BE57E953F089

    # /etc/pacman.conf
    [satukos]
    SigLevel = Required DatabaseRequired
    Server = https://github.com/inilvinilra/satukos-packages/releases/download/$arch
