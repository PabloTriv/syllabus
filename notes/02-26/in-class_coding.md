     case OP_BL:
       LN = IP + 1;
       next = IP + instruction.arg1;
       break;

     case OP_RET:
       next = reg[instruction.arg1];
       break;

     case OP_LD:
       reg[instruction.arg1] = mem[reg[instruction.arg2] + instruction.arg3];
       break;
       
     case OP_NOP:
       // do nothing
       break;
      
     case OP_HLT:
       fprintf(vmtrace, "done\n");
       exit(0);
       break;
