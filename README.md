# ALICE-Neural-Render

Neural rendering with TensorRT acceleration, SDF geometry, and real-time streaming

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-neural, alice-trt, alice-sdf, alice-view, alice-codec

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/render` | ニューラルレンダリング実行 |
| `POST` | `/api/v1/train` | NeRFモデル学習 |
| `POST` | `/api/v1/encode` | レンダリング結果エンコード |
| `GET ` | `/api/v1/models` | 学習済みモデル一覧 |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
