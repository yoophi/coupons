Coupons
======

> 아래는 미래의 소프트웨어 기능을 
> [Readme Driven Development](https://gist.github.com/stefanbirkner/835b7d0c498b4026f65a) 방식으로 미리 작성해본 내용입니다.

Coupons 는 재사용 가능한 쿠폰 서비스입니다. 

Coupons 를 이용하면 전자상거래나 기타 서비스에서 쿠폰 및 바우처를 생성하고 이를 사용해서 혜택을 지급받는 서비스를 개발할 수 있습니다.

## 설치

```
$ pip install coupons
```

## customize 및 실행

```
# wsgi.py
from coupons.entrypoints.flask_app import create_app

app = create_app()
```

```
$ gunicorn wsgi:app
```

## Endpoint 및 기능

전체 Endpoint 는 서비스 실행 후 `/openapi.json` 파일을 통해 확인할 수 있습니다.

### Admin API

- `GET /admin/api/coupon-groups`
- `GET /admin/api/coupons`

### User API

- `GET /api/current-user/coupons`
- `POST /api/current-user/coupons`

## Internal API

- `GET /internal/api/coupons`
- `POST /internal/api/coupons/{coupon-id}/use`

## Migration

```
$ coupons-service migration upgrade head
```

## Configuration

> TODO
