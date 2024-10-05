Subjects/ Topics: #Assembly #ARM 

- `mov r2, r1` - stores value of r1 in r2
- `move r4, #7` - stores value of 7 in r4
- `adds r3, r1, r2` - stores r1+r2 in r3
- `subs r3, r2, r1` - stores r2-r1 in r3
- `cmp r1, #7` - compares r1 to 7
- `ble <label>` - branch if less than or equal to

- For strange reasons, when dealing with big numbers make sure to
	- `ldr r3, =100000`

- Offset memory access:
	- `mov r1, #Table`
	- `ldr r0, [r1,8]`
	- Adds 8 to the address r1 then reads the data
	- So its like `r0 = Table[8]`

- Stacks:
	- Last in, first out system
	- Push and pop values to a stack
	- `push r3` - pushes value in r3 to stack
	- `pop r2` - pops the stack and stores the value in r2

- Link register
	- Branches with BL or BLX automatically put the return address in LR
	- If you jump to code with a branch you may need to return to next instruction in the calling code
	- Achieved by storing the return address in the program counter
```
instr1
instr2
branch mysub:
instr3
instr4

mysub:
  instr5
  instr6
  return
```
- Return returns back to instruction 3 to carry on program

- Return address using stack
	- Push RA onto stack, branch to subroutine
	- On return pop RA from stack and overwrite PC
- In arm the command is `lr`
- Need to push `lr` to the stack before another routine is called (and pop on return)
- Branches with BL or BLX put the return address in LR
- A subroutine can be return back to the caller with BX LR
- Or the subroutine code could store LR on the stack (push LR) then at the end
	- pop PC
	- To put the LR address into the PC from the stack

- When multiple functions are called within each other:
```
mov r0, #10
mov r1, #3
mov r2, #4
...
bl doadd:
...
doadd:
  @ code
  push lr
  bl epbee
  pop lr
  bx lr

epbee:
  @ more code
  bx lr
```
Pushing the link register and popping it off after the branch to get the original return address

