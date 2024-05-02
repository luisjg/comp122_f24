sth -- 
   errors detected
   a little better error messages
   output file

If no error on validate -- should we show the output and/or  EXITVAL
when do you print the correct EXITVAL

?
execute -- provide the output, EXITVAL, and summary count
validate -- provide the correct and actual ouptut
                    the correct and acutal EXITvalue
                    

\*_subroutine
  - exit value
  - null 
  - -L of just the appropriate suffex
     -L .  ===  -L `*.s`

templates
  - unify makefile
  - test
  - MD_git_cheatesheet  ==>  DEV_git_cheatsheet or just git_cheatsheet

use template for
  - sum
  - 1st assignment


Grading in the Fall:
   - Made changes in branching for grading
   - Take steps to double check grading steps for the first assignment



1. Assignments...
   1. First Assignment
   1. First Programming Assignment
      - simple java program
        - demo: 
           - write java program
           - 

      - use of Makefile
      - use of java_subroutine
      - use of sth

   1. sum... java code only
      - First Programming assigment is for participation
      1. write the java code (\*.j)
      1. use java_subroutine
      1. use make
      1. write several sth cases


Ideas for the Fall...

1. In mapping section bring up 
   - variables to locations in memory
   - variables to frames

1. Exercise in Mapping section
   - Talk about  "my stuff" and "common"  stuff -- apartment: bedroom versus kitchen
   - enumarate all the variables you have and organize them somehow
     - formal, locals, class, constants/final
   - enumerate all of the registers into groups
      - (reserved: gp, at, k1, k2), T-s, S-es, a-s, v-s, fp, sp



Update mips_subroutine / java_subroutine
   - to return an appropriate $?
   - to remove the extra banner information
     * banner should be added only if print_register is called, etc.
     * i.e., the default output is NUL and not the register
     * this makes the output more like MARS with a list of registers to present as an option

   - update to remove suffix name with the -L option,
     * automatically insert the appropriate suffix
       - mips_subroutine -L `foo` : includes foo.a
       - java_subroutine -L  `*`  : includes *.j
     * pathentally, allow the -L option to be a path-spec
       - expand, then only include the appropriate  .{SUFFIX} at the end
     *  -L '*'  ==>  *.j


1. validate the output placement and redirection:  tty, /dev/stdin, /dev/stdout




1. Error in java_subroutine....
Testing: java_subroutine   
Usage:  mips_sub [ option ... ] name [ arg ... ]



## Multiplication
   - [ ] update the slides to include cost analysis
   - based upon the timing chart, multiplication take ?32
   - revisit writing a multiplication using the tricks...


## Activiation Records Lecture
   - use Miro
   - have a scattering of formals and locals
   - have a scattering of registers
   - group them
   - talk about the catagors: 
       - location: shared vurses private: 
       - value: shared vurses private: 

   - reorganize the stuff into a box: i.e., a activation frame
   - [ ] Develop a new set of slides associated with frames

## TAC
   - [ ] Consider having a special section on Boolean expressions
     - then loops and conditions use b-gtz for true
       ```mips
       slti    $t3, $t1, 5         # if i < 5 goto done
       bgtz    $t3, done           # 
       ```

     - pseudo instruction
       * bset  $t3, done   --> bgtz
       * bclear $t3, done  --> bz (syname:  bne,  beq $t3, $zero, done)

     * note that b can be an immediate
       - a == b:   seq  $at, a, b
       - a <= b    sle  $at, a, b
       - a < b     slt  $at, a, b
       - a > b     sgt  $at, a, b
       - a >= b    sge  $at, a, b
       - a != b    sne  $at, a, b

  - [ ] Consider creatint an ARM version for TAC
  - [ ] Consider notation for preshifts
    - Nope this would be better as a peep-hole optimizer
      *  x = x op imm
      *  x = x op y
      *  x = x op (shift)    # extended version for ARM
      *  x = x op ( b << imm)

      ```
      y = b << imm
      z = z op y
      ```
      =>
      ```
      z = z op (b << imm)
      ```


