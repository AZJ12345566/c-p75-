c-p75-
c p75作业讲解
1.计算结构体大小
      typedef struct
      {
            int a;//0-3
            char b;//4
            //5
            short c;//6-7
            short d;//8-9
      }AA_t；
      //10个字节
      //结构体的总大小必须为最大对齐数的整数倍
      //所以最终大小为12个字节
   
   
   //默认为4个字节对齐
   struct A
   {
        char a;//0-3
        short b;//4-5
        //6-7
        int c;//8-11
        char d;//12
        //13-15
   };//16
   struct B
   {
        int a;//0-3
        short b;//4-5
        char c;//6
        //7
        int d;//8-11
   };//12
   
   
   #pragma pack(4)//按照4个字节对齐
  int main(int argc, char* argv[])
  {
        struct tagTest1
        {
              short a;//0-1
              char d;//2
              //3
              long b;4-7
              long c;//8-11
        };//12
        struct tagTest2
        {
              long b;0-3
              short c;//4-5
              char d;//6
              //7
              long a;//8-11
        };//12
        struct tagTest3
        {
              short c；//0-1
              //2-3
              long b;////4-7
              char d;//8
              //9-11
              long a;//12-15
        };//16
        struct tagTest1 stT1;
        struct tagTest2 stT2;
        struct tagTest3 stT3;
        printf("%d %d %d",sizeof(stT1),sizeof(stT2),sizeof(stT3));
        return 0;
  }
  #pragma pack()
   
   
   
   
   
