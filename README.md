# TINYsim

Simulation program for Conor McBride's TINY Machine.

Example - Correct Output

```f
The following inputs are for the starter trace (What you're given)
-------------------------------------------------------------------
Enter input queue (Format: x, x, x, x...): 0, 0, 1, C, 0, 7, C, A
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 0 0 0 0 65F65E65D65C8F70

The following inputs are for the trace to check
-----------------------------------------------
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 3 0 2 0 65F65E65D65C8F70 
Enter the final piece of the trace (format xxx x x x): GET - 0 -
I L F A  Memory----------  Action---
P I R C  0123456789ABCDEF  OPR & ? !
-------  ----------------  ---------
3 0 2 0  65F65E65D65C8F70  GET - 0 - <-- YOUR INPUT
-------  ----------------  ---------
TRACE INPUT CORRECT <-- TRACE OUTPUT
Hit Enter to Finish...
```

Example - Incorrect Registry Config

```f
The following inputs are for the starter trace (What you're given)
-------------------------------------------------------------------
Enter input queue (Format: x, x, x, x...): 0, 0, 1, C, 0, 7, C, A
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 0 0 0 0 65F65E65D65C8F70

The following inputs are for the trace to check
-----------------------------------------------
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 3 0 1 0 65F65E65D65C8F70 
Enter the final piece of the trace (format xxx x x x): GET - 0 -
I L F A  Memory----------  Action---
P I R C  0123456789ABCDEF  OPR & ? !
-------  ----------------  ---------
3 0 2 0  65F65E65D65C8F70  GET - 0 - <-- YOUR INPUT
-------  ----------------  ---------
ERROR WITH REGISTRY  <-- TRACE OUTPUT
Hit Enter to Finish...
```

Example - Incorrect Memory Config

```f
The following inputs are for the starter trace (What you're given)
-------------------------------------------------------------------
Enter input queue (Format: x, x, x, x...): 0, 0, 1, C, 0, 7, C, A
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 0 0 0 0 65F65E65D65C8F70

The following inputs are for the trace to check
-----------------------------------------------
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 3 0 2 0 55F65E65D65C8F70 
Enter the final piece of the trace (format xxx x x x): GET - 0 -
I L F A  Memory----------  Action---
P I R C  0123456789ABCDEF  OPR & ? !
-------  ----------------  ---------
3 0 2 0  65F65E65D65C8F70  GET - 0 - <-- YOUR INPUT
-------  ----------------  ---------
ERROR WITH MEMORY <-- TRACE OUTPUT
Hit Enter to Finish...
```

Example - Incorrect Action Config

```f
The following inputs are for the starter trace (What you're given)
-------------------------------------------------------------------
Enter input queue (Format: x, x, x, x...): 0, 0, 1, C, 0, 7, C, A
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 0 0 0 0 65F65E65D65C8F70

The following inputs are for the trace to check
-----------------------------------------------
Enter TINY configuration (Format: x x x x  xxxxxxxxxxxxxxx): 3 0 2 0 65F65E65D65C8F70 
Enter the final piece of the trace (format xxx x x x): GET - 1 -
I L F A  Memory----------  Action---
P I R C  0123456789ABCDEF  OPR & ? !
-------  ----------------  ---------
3 0 2 0  65F65E65D65C8F70  GET - 0 - <-- YOUR INPUT
-------  ----------------  ---------
ERROR WITH ACTIONS <-- TRACE OUTPUT
Hit Enter to Finish...
```

## How To Use

+ Run the script with Python 3 (3.10 tested)
+ Input a TINY input queue in the format "x, x, x, x..."
+ Input a starting TINY configuration in the format "x x x x  xxxxxxxxxxxxxxx"
+ Input a TINY configuration to check for in the format "x x x x  xxxxxxxxxxxxxxx"
+ Input a TINY action configuration to check for in the format "xxx x x x"
+ The program should then print if your TINY config and action are correct, if it is not it should tell you where

## Notes

+ This script halts after 500 operations, and assumes that the TINY program loops indefinitely
+ This can be changed by editing the main loop of the program, line 298. Set count to a desired value.
+ There are some use cases where this may trip up, do let me know

## Known Bugs

### Currently No Known Bugs
