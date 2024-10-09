drvoid@q:/dev$ sudo blkid
/dev/sda2: UUID="ff5c75f5-6b8d-4522-835e-9169c3d06417" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="c8c6656f-390d-40cd-81a2-5010c7863a7e"
/dev/sdb1: LABEL="env-server" UUID="5a87fa4f-d088-4844-9d36-649e42ab4268" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="kutularim" PARTUUID="8c963ef8-1203-4d53-a9a6-c5a88ac54a68"
/dev/sda1: UUID="15A7-AB22" BLOCK_SIZE="512" TYPE="vfat" PARTLABEL="EFI System Partition" PARTUUID="96243d57-a91f-4e67-9ccd-d515e6f13844"
/dev/vda1: LABEL="ailib" UUID="342c7d22-6b42-4fdf-9bbd-1f53f5376523" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="29d3c8a1-d9e2-4bd5-b20a-e5a4208620c0"


# /dev/sdb1 (env-server)
UUID=5a87fa4f-d088-4844-9d36-649e42ab4268 /media/drvoid/env-server ext4 defaults,nofail 0 2

# /dev/vda1 (ailib)
UUID=342c7d22-6b42-4fdf-9bbd-1f53f5376523 /media/drvoid/ailib ext4 defaults,nofail 0 2