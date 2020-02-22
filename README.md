# pcdos-olddos
This is a batch file for adding the relevant files from ``OLDDOS.EXE`` to IBM PC DOS 7.01 (IBM PC DOS 2000).  Please verify that you have valid licenses to use the tools referenced here prior to obtaining them.

In order to use this, you need the following:
* An existing PC-DOS 7.01 (PC-DOS 2000) installation, US English release
* [``OLDDOS.EXE``](https://archive.org/details/olddos) (SHA256 sum d06ed2a259d854cf7a7f96a1e1ec1951e6399aa3b9dc613035414ff5b7709fd5)

Once you have the ``OLDDOS.EXE`` file, run it on a system that can run 16-bit DOS applications to extract it.  An unzipping program may be able to extract it as well, but this is untested.

From there, copy the below files to a floppy disk or other location to be used for patching, and copy ``PCOLDDOS.BAT`` to the same location.

The files this batch file copies to the installation, along with their associated SHA256 sums:

    CHKSTATE.SYS  8e28aaec61091ca0b24dcc23b1687d20d47aed8d8282cfbc11c9a86cb7accaff
    MEMMAKER.EXE  9fd4660ab67f533855a7338399feced63ca434f59c3b799466836f73ea855000
    MEMMAKER.HLP  2f70e0832f9ca524d85cd2749c6945cc3e6f4e01cfc46bba926754931ff26982
    MEMMAKER.INF  5a0caba1f5371024e03189733111c14921ef005ed00c6d8282366ad5002e4c8f
    PRINT.EXE     fbf666f03287031f4e010de0b9f40db52a9420914c08dc7a51414227f37bc930
    QBASIC.EXE    dbfd7e7d27fea72877c5332551889b3d3c46fc5b72d15e35e232ea611570a2cd
    QBASIC.HLP    8c8d8a9004c18d56e0cd30d22fb17d7351ef7cdca5e1d7407c0b345572235e95
    RESTORE.EXE   7e298f385a7b7b4559f2325ce7e1a8b75bf90228f3bc6af0764869ce61dad795
    SIZER.EXE     a36286ce956647116beec02bd793a1db92b2448e64e59725aae48328e20dd8e3

Finally, this batch file uses MD5 digests to check whether the patch files and the files to be patched are the expected files.  Note that MD5 isn't a secure hashing algorithm at this point.  If there are questions about the legitimacy of the files, a more secure hashing algorithm (such as SHA256) is strongly encouraged instead.  The intent of using MD5 was primarily to prevent accidental application of this patch to a system which is not suited for it while not requiring an implementation of a hashing algorithm which would likely be extremely slow on a computer of the era that runs DOS.

Because DOS does not have a native MD5 tool, ``MD5SUM.EXE`` (SHA256 sum 484e05c00662d260c95a3a11e5922b465d14ead71a8950cd54193c32bcebd4c7)from https://github.com/Kreeblah/md5sum is also required.

To use this batch file, switch to the location where it's located and run:

``pcolddos [DRIVE] [DOSDIR]``

``[DRIVE]`` should indicate the drive where PC-DOS 7.01 is currently installed, and ``[DOSDIR]`` should indicate the directory it's installed in.  For example, if PC-DOS 7.01 is installed in ``C:\DOS`` then you could use the following command to apply the patch:

``pcolddos c: dos``