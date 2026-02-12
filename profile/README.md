# A4AD Team

**A4AD Forum**  
Простой, современный и масштабируемый форум для сообществ

[![GitHub Org](https://img.shields.io/badge/Org-A4AD-181717?logo=github)](https://github.com/A4AD-team)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Early%20Development-yellow)](https://github.com/A4AD-team)
[![Go](https://img.shields.io/badge/Go-1.23+-00ADD8?logo=go)](https://go.dev/)
[![NestJS](https://img.shields.io/badge/NestJS-10+-E0234E?logo=nestjs)](https://nestjs.com/)

## Что это

A4AD — это **лёгкий и современный форум**, который можно запустить для любого сообщества: от локальных клубов и хобби-групп до внутренних корпоративных обсуждений и открытых проектов.

Цель — сделать платформу, которую легко развернуть, поддерживать и кастомизировать, без лишней сложности.

### Основные возможности (на данный момент в разработке)

- Регистрация, авторизация, роли (user / moderator / admin)  
- Публичные и редактируемые профили пользователей  
- Создание, редактирование, удаление постов  
- Дерево комментариев с ответами и лайками  
- Уведомления о комментариях, ответах, лайках, упоминаниях  
- Микросервисная архитектура для удобного масштабирования  

## Текущий статус (февраль 2026)

- Early Development → активно пишем core-сервисы  
- MVP (базовый форум с постами и комментариями) — планируем к Q2 2026  
- Первая публичная версия (open-source) — ориентировочно Q3 2026  

## Архитектура и стек

| Компонент              | Язык / Фреймворк          | База данных / Хранилище     | Кратко о назначении                     |
|------------------------|----------------------------|------------------------------|------------------------------------------|
| API Gateway            | Go / Fiber                 | —                            | Единая точка входа, JWT, rate-limit      |
| Auth Service           | Java / Spring Boot         | PostgreSQL                   | Регистрация, логин, JWT, роли            |
| Profile Service        | Go                         | PostgreSQL                   | Профили, аватар, статистика              |
| Post Service           | Go                         | PostgreSQL                   | Посты, CRUD, счётчики                    |
| Comment Service        | NestJS                     | MongoDB                      | Комментарии (threaded), лайки            |
| Notification Service   | NestJS                     | Redis + PostgreSQL/MongoDB   | Уведомления (in-app, email)              |

**Инфраструктура и observability**  
- Docker + docker-compose (для локальной разработки)  
- Kubernetes-ready (в планах Helm-чарты)  
- OpenTelemetry, Prometheus, Grafana  
- Redis Pub/Sub или Kafka для событий (в процессе выбора)  

## Структура репозиториев (multi-repo)

- [api-gateway](https://github.com/A4AD-team/api-gateway)  
- [auth-service](https://github.com/A4AD-team/auth-service)  
- [profile-service](https://github.com/A4AD-team/profile-service)  
- [post-service](https://github.com/A4AD-team/post-service)  
- [comment-service](https://github.com/A4AD-team/comment-service)  
- [notification-service](https://github.com/A4AD-team/notification-service)  
- [docs](https://github.com/A4AD-team/docs) — документация, схемы, ADR  
- [infra](https://github.com/A4AD-team/infra) — terraform, helm, ansible (будет позже)  

## Как подключиться / внести вклад

- **GitHub Discussions** — вопросы, идеи, предложения по фичам  
- **Issues** — баги и конкретные задачи  
- **Pull Requests** — очень приветствуются (см. CONTRIBUTING.md в каждом репозитории)  
- **Email** — team@a4ad.dev  

Мы открыты к коллаборации: ищем единомышленников для core-команды и open-source участников.

Присоединяйтесь — строим удобный форум вместе! 🚀
