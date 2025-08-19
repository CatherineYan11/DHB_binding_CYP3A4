# DHB_binding_CYP3A4
MD simulation inputs:
pmemd.cuda -O -i em.in -p New.tleap.top -c New.tleap.inpcrd -o new.em.out -r new.em.rst -inf new.em.mdinfo
pmemd.cuda -O -i nvt.in -p New.tleap.top -c new.em.rst -ref new.em.rst -o new.nvt.out -x new.nvt.crd -r new.nvt.rst -inf new.nvt.mdinfo
pmemd.cuda -O -i npt.in -p New.tleap.top -c new.nvt.rst -ref new.nvt.rst -o new.npt.out -x new.npt.crd -r new.npt.rst -inf new.npt.mdinfo
pmemd.cuda -O -i pre_md.in -p New.tleap.top -c new.npt.rst -ref new.npt.rst -o new.pre_md.out -x new.pre_md.crd -r new.pre_md.rst -inf new.pre_md.mdinfo
pmemd.cuda -O -i md.in -p New.tleap.top -c new.pre_md.rst -ref new.pre_md.rst -o new.md.out -x new.md.crd -r new.md.rst -inf new.md.mdinfo
pmemd.cuda -O -i md.in -p New.tleap.top -c new.md.rst -ref new.md.rst -o new.md01.out -x new.md01.crd -r new.md01.rst -inf new.md01.mdinfo



MSM inputs:
python -i msm.in

smd inputs:
pmemd.cuda -O -i asmd_1.1.mdin -p New.tleap.top -c ../new.pre_md.rst -ref ../new.pre_md.rst -r ASMD_1.1.rst7 -o ASMD_1.1.mdout -x ASMD_1.1.nc -inf ASMD_1.1.info
