# A4AD Team

**Approval Automation for Agile Departments**  
Современный движок бизнес-процессов и согласований для малого и среднего бизнеса

[![GitHub](https://img.shields.io/badge/GitHub-A4AD-181717?logo=github)](https://github.com/A4AD)
[![License](https://img.shields.io/badge/MIT%20-red.svg)](https://opensource.org/licenses/MIT)
[![Go](https://img.shields.io/badge/Go-1.23+-00ADD8?logo=go)](https://go.dev/)
[![Status](https://img.shields.io/badge/Status-Pre--Alpha-orange)](https://github.com/A4AD)

## О проекте

- легковесный, масштабируемый **движок согласований** (approval workflow engine), созданный специально для небольших и средних компаний, где нужно быстро и надёжно согласовывать:

- отпуска и больничные
- закупки и командировки
- счета и платежи
- любые кастомные заявки

Мы делаем систему, которую можно развернуть за часы, а не месяцы, и которая не требует отдельного BPM-специалиста.

**Ключевые принципы:**
- Микросервисная архитектура с минимальным coupling
- Event-driven + REST + GraphQL-ready
- Гибкие workflow (в т.ч. параллельные этапы и условия)
- Полная аудит-трассировка и уведомления
- Поддержка делегирования, доработок и отмен

## Текущий статус (февраль 2026)

- Pre-Alpha / внутренний MVP
- Идёт активная разработка core-сервисов
- Планируем первую закрытую бету — Q2 2026

## Архитектура и стек (2026)

| Компонент              | Язык / Фреймворк          | База данных / Хранилище     | Примечание                              |
|------------------------|----------------------------|------------------------------|-----------------------------------------|
| Auth Service           | Java / Spring Boot         | PostgreSQL                   | IAM + JWT + RBAC                        |
| Workflow Service       | Go                         | Neo4j (graph)                | Графовые маршруты + условия             |
| Request Service        | Go                         | PostgreSQL                   | Жизненный цикл заявок                   |
| Comment Service        | NestJS / TypeScript        | MongoDB                      | История комментариев                    |
| Audit Service          | Go                         | ClickHouse                   | Append-only логи + аналитика            |
| Notification Service   | NestJS                     | Redis + Kafka                | Email / in-app / reminders              |
| Scheduler Service      | Go                         | Redis / PostgreSQL           | Таймауты, напоминания, эскалации        |
| API Gateway            | Go / Fiber                 | —                            | Routing, auth, rate-limit, tracing      |

**Инфраструктура & Observability**
- Docker + docker-compose (dev)
- Kubernetes-ready (Helm charts в планах)
- OpenTelemetry + Prometheus + Grafana / Loki
- Kafka для событий

## Структура репозиториев

- [A4AD/auth-service](https://github.com/A4AD-team/auth-service)
- [A4AD/workflow-service](https://github.com/A4AD-team/workflow-service)
- [A4AD/request-service](https://github.com/A4AD-team/request-service)
- [A4AD/comment-service](https://github.com/A4AD-team/comment-service)
- [A4AD/audit-service](https://github.com/A4AD-team/audit-service)
- [A4AD/notification-service](https://github.com/A4AD-team/notification-service)
- [A4AD/scheduler-service](https://github.com/A4AD-team/scheduler-service)
- [A4AD/api-gateway](https://github.com/A4AD-team/api-gateway)
- [A4AD/docs](https://github.com/A4AD-team/docs) — документация, схемы, ADR
- [A4AD/infra](https://github.com/A4AD-team/infra) — terraform / helm / ansible

## Связаться с нами

- GitHub Discussions → для вопросов и идей
- Issues → только баги и фича-реквесты
- Email: team@openfly.tech
