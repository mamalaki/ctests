#include <stdio.h>
#include <stdlib.h>

typedef struct tTMsg {int a;} tTMsg;

typedef enum
{
    LRDC_COA_MSG_INCOMING_COA,

    LRDC_COA_MSG_INCOMING_MAX,
} tlrdcCoa_MsgType;

typedef struct lrdcCoa_MsgHdr
{
    tlrdcCoa_MsgType type;
    tTMsg            link;  /* to link in msg Q */
} tlrdcCoa_MsgHdr;

typedef struct lrdcCoa_CoaMsg
{
    union
    {
        tlrdcCoa_MsgHdr hdr; /* must be 1st field of every msg! */
    } u;
    int gwId;
    void* message;
} tlrdcCoa_CoaMsg;

int main(void) {
    tlrdcCoa_CoaMsg *pMsg = malloc(sizeof(tlrdcCoa_CoaMsg));
    *pMsg = (tlrdcCoa_CoaMsg){ 
        .u.hdr.type = LRDC_COA_MSG_INCOMING_COA, 
        .u.hdr.link = {0},
        .gwId    = 1, 
        .message = NULL,
    };
  printf("Hello World\n");
  return 0;
}
