Toasty Hex Editor (e2_hex_edit)
=============
Hex editor for Garry's Mod Expression 2 gate. Can be wirelinked to a hard drive gate. Data is pulled from the drive
into the gate memory for editing. After editing, push the changed data back to the drive using the device access
commands listed below.

Commands avaliable (also in the gate code):
```

EDITOR COMMANDS (all numerical arguments are in hex!):
>x X1 X2          - Dumps hex from memory address X1 to X2
>xn X1 N          - Dumps N hex digits starting from address X1
>xa X1 X2         - Same as '>x' but outputs ASCII only
>xna X1 N         - Combines '>xn' and '>xa': outputs N ASCII characters starting from X1
>w X1 D1 D2 D3... - Writes a variable number of hex bytes (D#) to memory starting at address X1
>wa X1 S          - Writes a variable length ASCII string (S) to memory starting at address X1
>q                - Ends any currently running task immediately
>rst              - Soft-reset the device, does not erase internal memory
>lclear           - Erases internal memory, cannot be undone!

DEVICE ACCESS COMMANDS:
>sv LO RO N       - Copies a data block from internal memory to the remote device 'DEVICE' (RAM, DHDD, etc.)
					LO = Local Memory Offset
					RO = Remote Memory Offset
					N  = Copies N number of bytes
					example: 
						>sv 200 1F FF ; copies 256 bytes (N) from Local memory address 0x200 (LO)
						              ; to Remote Memory address 0x1F (RO)
>rd LO RO N       - Same as '>sv' but reads to internal memory. BE CAREFUL, the position of LO and RO 
                    haven't changed! LO always comes first!
>bsv LS LE RS
>bsv RS RE LS
```
