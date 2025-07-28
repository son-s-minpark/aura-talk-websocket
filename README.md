# 🌐 AuraTalk WebSocket 테스트

## 📋 기본 정보

| 항목 | 값 |
|------|-----|
| **서버 도메인** | `https://api.auratalk.kro.kr` |
| **SockJS URL** | `https://api.auratalk.kro.kr/ws` |
| **WebSocket URL** | `wss://api.auratalk.kro.kr/ws/websocket` |
| **테스트 페이지** | `https://son-s-minpark.github.io/aura-talk-websocket/` |

1. **회원가입**: POST `/api/users`
```json
{
  "email": "test1234@gmail.com",
  "password": "Test1234!"
}
```
2. **로그인**: POST `/api/users/login`
3. **채팅방 생성**: POST `/api/chatrooms`
4. **토큰 복사**: 응답의 `token` 필드 값 복사

### 🧪 연결 실패 시 체크리스트
- [ ] JWT 토큰이 유효한가?
- [ ] 토큰에 "Bearer " 접두사가 있나? (헤더에만 추가)
- [ ] HTTPS/WSS 프로토콜을 사용하고 있나?
- [ ] 브라우저 콘솔에 CORS 오류가 있나?
- [ ] 서버가 정상 작동하고 있나? (`/api/health` 확인)

## 📋 테스트 체크리스트

```
✅ 서버 상태 확인 (GET /api/health)
✅ JWT 토큰 발급 (POST /api/users/login)
✅ WebSocket 연결 성공
✅ 채팅방 구독 (SUBSCRIBE /topic/chatroom/{id})
✅ 메시지 전송 (SEND /app/chat/{id})
✅ 메시지 수신 확인
✅ 연결 해제 (DISCONNECT)
```

위 방식으로 AuraTalk 서버의 WebSocket 연결을 테스트할 수 있습니다! 🎉
