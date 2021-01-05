# partiallyFulfilled
Partially refunded Order, Partially fulfilled Order

"부분 환불" 및 "부분 배송처리" 상태의 주문 건 처리에 대한 협의안 및 수정

#현재#
partially refunded 상태 오더는 DB에 저장하지 않음
- payment status: paid,
- fulfillment status: unfulfilled 
위 두 조건일 때만 오더 저장


#요청사항
1. partially refunded 상태의 주문도 처리할 수 잇게 해달라고 요청하면 수작업으로 order_code 조회->API전송->DB저장
-> 자동으로 가져올 수 있게 처리 요청
    - 문제: 부분환불 되는 시점이 예측 불가
2. partially fulfilled 상태 주문 역시 처리 가능하도록 요청
- 여러 제품 중 일부만 주문처리하고 미처리된 주문을 다시 재처리
 - 문제: SQL 중복 키 발생 및 수정 반영 시 현재 시스템 영향 큼
