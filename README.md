# t1650-libreboot
ROM files for Dell Precision T1650 / Optiplex 7010 (and the 9010 in theory).

## Intro

Libreboot is a project designed to replace your computer's proprietary BIOS with free (libre) firmware. 

While the Dell Precision T1650 and Optiplex 7010 are old by today's standards, they're new enough to support hardware capable of heavier workloads like video editing, CAD, and virtualisation. These machines are also very common, cheap, and use fairly standard desktop hardware, so you can easily add/upgrade hardware (like the RAM, storage, graphics card, and power supply).

## Why this repository exists

The problem with this machine is that it's one of Libreboot's [Binary Blob Reduction Policy](https://libreboot.org/news/policy.html) machines. If you flash one of the release ROMs from Libreboot's website for this machine without any modification, the computer will not be post because these ROMs do not include the proprietary vendor files (which are unfortunately required for the machine to post).

You can either inject the vendor files into a release ROM or you can compile the ROM yourself using [lbmk](https://libreboot.org/docs/build/). However, I ran into some problems doing either of these on Debian/Ubuntu, so I compiled Libreboot in an Arch Linux VM.

TLDR - this repo exists for the sake of convenience and so you don't have to go as much pain as I went into lol.

## WARNING

While I have tested these ROMs and you are free to use them, you use them at your own risk. I suggest you read the documentation provided by Libreboot so you know what you're getting yourself into. I will not take responsibility for your bricked machine.

## Checksums (SHA256)

Verify the checksums to ensure the integrity of the ROMs. To do this, use the `sha256sum` command line tool:

- libreboot.rom: `5cde4beeda8fa5dd8ce5d60e842a2ad15b48800f957d75da083020f52ccd0bed`
- 4mb.rom: `dc70bc00acd7a97d88dbc314891e2be6bf807cf09e3445d17eff875d7dd3755b`
- 8mb.rom: `e9c76613e111b3ab7209dd9aeae3eddfb99382d9a095b3970670e1de73b4a23e`

`libreboot.rom` is the original 12MB ROM that I compiled. However, this computer's motherboard has two flash chips (either 2 x SOIC-8 or SOIC-8 + SOIC-16) so the ROM has to be split into different files, which I have already done for you, but I left the original 12MB ROM here as it may be helpful.

If your motherboard has an SOIC-16 flash chip, that one will be for the 8MB ROM. Mine has two SOIC-8 chips (the left one is for the 4MB ROM, the right one is for the 8MB ROM).

## Additional Notes/Resources

If you're not using a dedicated GPU, make sure your CPU has integrated graphics. If you are using a dedicated GPU, I would suggest using a CPU without integrated graphics. 

- [My video about Libreboot on the T1650](https://www.youtube.com/watch?v=HxsQ4j8U_Fk)
- [T1650 Libreboot Documentation](https://libreboot.org/docs/install/t1650.html)
- [External Flashing Documentation](https://libreboot.org/docs/install/spi.html) (I used the CH341A which Libreboot advises against... idk whether you should use it, but it seems to work fine as long as it's wired correctly)

If you have any concerns, [DM me on Matrix](https://matrix.to/#/@notnapoleon:envs.net) or [email me](mailto:taz@notnapoleon.net). 

## Future Potential

It's theoretically possible to Libreboot this machine internally. I may try this out when I have the time and resources to. So maybe one day, you can have a fast, librebooted desktop without needing to jump through a bunch of hurdles... maybe :)
