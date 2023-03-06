/*Pallav Regmi*/
/*Getbits*/


#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
unsigned long read_ulong(void);
unsigned int get_bits(unsigned int x, int p, int n);
void errFunc(); /* Error checking function */
unsigned x;
int p,n;
bool x_overflow, position_out_of_range,num_bits_out_of_range,too_many_bits;
int main (void)
{
  while (true)
    {
    x_overflow = false;
    x = read_ulong();
    p = (int) read_ulong();
    n = (int) read_ulong();
    position_out_of_range = p > 31;
    num_bits_out_of_range = n > 31;
    too_many_bits = n > (p + 1);
    errFunc();
    }
    return 0;
}
void errFunc()
{
     if (x_overflow)
       {
      printf("Error: value out of range\n");
       }
     else if (position_out_of_range)
       {
      printf("Error: position out of range\n");
       }
     else if (num_bits_out_of_range)
       {
      printf("Error: number of bits out of range\n");
       }
     else if (too_many_bits)
       {
      printf("Error: too many bits requested from position\n");
       }
     else
       {
       printf("getbits(x=%u, p=%d, n=%d) = %u\n", x, p, n, get_bits(x, p, n));
       }
  }
  unsigned long read_ulong(void) {
  double number = 0;
  char c;
  bool state = false;
  while (!state) {
    c = getchar();
    if (c == EOF) exit(0);
    else if (c >= '0' && c <= '9')
      {
      number *= 10;
      number += c - '0';
      if (number > 0xffffffff)
{
        x_overflow = true;
}
      }
    else
      {
      state = true;
      }
  }
  return number;
}
unsigned int get_bits(unsigned int x, int p, int n) {
  return (x >> (p + 1 - n)) & ~(~0 << n);
}
