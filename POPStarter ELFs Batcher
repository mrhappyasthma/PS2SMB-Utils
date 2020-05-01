@echo off

set @pop_path=smb:/POPS/
set @pop_pre=SB.
set @pop_op=Network

if not exist "POPSTARTER.BAK" (
	if not exist "POPSTARTER.ELF" (
		echo Need POPSTARTER.ELF or POPSTARTER.BAK file
		pause
		GOTO :EOF
	)
	copy /Y POPSTARTER.ELF POPSTARTER.BAK > NUL
)
echo Started generating elfs for "%@pop_op%" method.
del *.ELF
for %%f in (*.VCD) do (
  copy /Y POPSTARTER.BAK "%@pop_pre%%%~nf.ELF" > NUL
) 
copy /Y POPSTARTER.BAK POPSTARTER.ELF > NUL

echo Process finished
pause
