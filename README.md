# My CI/CD Test

Next.js 16 기반으로 CI/CD 자동화를 실험해보는 테스트용 프로젝트입니다.

## Stack

- Next.js 16
- React 19
- TypeScript
- Tailwind CSS 4

## Local Development

```bash
npm install
npm run dev
```

브라우저에서 `http://localhost:3000`을 열면 됩니다.

## Available Scripts

- `npm run dev`: 개발 서버 실행
- `npm run lint`: ESLint 검사
- `npm run typecheck`: TypeScript 타입 검사
- `npm run build`: 프로덕션 빌드
- `npm run start`: 프로덕션 서버 실행

## CI

GitHub Actions workflow는 `.github/workflows/ci.yml`에 있습니다.

푸시 또는 Pull Request 시 아래 순서로 검증합니다.

1. `npm ci`
2. `npm run lint`
3. `npm run typecheck`
4. `npm run build`

## Deployment

테스트 목적이면 Vercel 배포가 가장 간단합니다.

### 추천 이유

- Next.js와 궁합이 가장 좋음
- GitHub 저장소 연결만 하면 Preview 배포 자동 생성
- 별도 서버 세팅 없이 바로 확인 가능
- 작은 테스트 프로젝트는 운영 부담이 거의 없음

### 권장 흐름

1. 이 프로젝트를 GitHub에 푸시
2. Vercel에서 저장소 import
3. Framework는 `Next.js`로 자동 감지
4. 기본 설정 그대로 배포
5. 이후 `main` 브랜치 푸시 시 Production 배포, Pull Request 생성 시 Preview 배포 사용

### Vercel에서 보통 쓰는 방식

- `main` 브랜치: 실제 배포용
- feature 브랜치 / Pull Request: 미리보기 배포용

이 프로젝트처럼 CI/CD 연습이 목적이면 이 구성이 가장 편합니다.

## Next Steps

- GitHub 저장소 생성 및 푸시
- Vercel 프로젝트 연결
- 필요하면 `test` 스크립트 추가 후 CI에 포함
- 배포 보호가 필요하면 `main` 브랜치 보호 규칙 추가
