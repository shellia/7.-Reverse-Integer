Reverse digits of an integer.

Example1: x = 123, return 321
Example2: x = -123, return -321

click to show spoilers.

Note:
The input is assumed to be a 32-bit signed integer. Your function should return 0 when the reversed integer overflows.



class Solution {
public:
    int reverse(int x) { 
        char s1[18];
        int len = sprintf(s1, "%d", x);
        int i,j=0;
        char sOut[18];
        if(s1[0] == '-')
        {
            sOut[0] = '-';
    
            for(i=len-1; i>0; i--)
            {
                j++;
                sOut[j] = s1[i];
            }
        }
        else 
        {
            
            for(i=len-1; i>=0; i--)
            {
                sOut[j] = s1[i];
                j++;
            }
        }
        sOut[len] = '\0';
        int nResult = 0;
        char strFormat[12];
        sprintf(strFormat, "%%0%dd", len);
        sscanf(sOut, "%d", &nResult);
        char NumTemp[18];
        sprintf(NumTemp, strFormat, nResult);

        if( strcmp(NumTemp, sOut) != 0) 
        {
            return 0;
        }
        else 
        {
            return nResult;
        }
    }

};
