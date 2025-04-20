```
#include <string.h>
#include <stdio.h>

int main() {
  char *src="hello, world";
  int len = strlen(src);
  int size = sizeof(src);
  printf("strlen=%d, size=%d\n", len, size);
  return 0;
}
```
strlen=12, size=13

```
#include <string.h>
#include <stdio.h>
#include <stdlib.h>

int main()
{
	char *src="hello,world";
	char* dest=NULL;
	int len=strlen(src);
	dest=(char*)malloc(len);
	char* d=dest;
	char* s=&src[len-1];
	while(len--!=0)
		*d++=*s--;
	printf("%s",dest);
	free(dest);
	dest=NULL;
	return 0;
} 
```
