<h1 align="center">Share Ur Save</h1>

![TypeScript](https://img.shields.io/badge/TypeScript-grey?style=flat-square&logo=typescript)
![NestJS](https://img.shields.io/badge/NestJS-grey?style=flat-square&logo=nestjs)
![Next.js](https://img.shields.io/badge/Next.js-grey?style=flat-square&logo=next.js)
![Node.js](https://img.shields.io/badge/Node.js-grey?style=flat-square&logo=node.js)
![ESLint](https://img.shields.io/badge/ESLint-grey?style=flat-square&logo=eslint)
![Prettier](https://img.shields.io/badge/Prettier-grey?style=flat-square&logo=prettier)
![Docker](https://img.shields.io/badge/Docker-grey?style=flat-square&logo=docker)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-grey?style=flat-square&logo=postgresql)
![Redis](https://img.shields.io/badge/Redis-grey?style=flat-square&logo=redis)
![Nginx](https://img.shields.io/badge/Nginx-grey?style=flat-square&logo=nginx)

## Architecture

```mermaid
    graph BT
        subgraph App[<b>App</b>]
            subgraph Frontend[<b>Frontend</b>]
                Website[<b>Website</b><br /><ul><li>Next.js</li><li>Redux</li></ul>]
            end

            subgraph Backend[<b>Backend</b>]
                API[<b>API</b><br /><ul><li>NestJS</li><li>Express</li><li>Prisma</li></ul>]
                Postgres[<b>PostgreSQL</b><br /><i>Store data</i>]
                Redis[<b>Redis</b><br /><i>Store sessions</i>]
                API <--> Postgres
                API <--> Redis
            end

            Website <-- HTTP/HTTPS --> API
            Nginx[<b>Nginx</b>]
            Nginx --> API
            Nginx --> Website
        end

        Client[<b>Client</b>]
        Client <-- HTTP/HTTPS --> Nginx
```

## Database Schema

```mermaid
    graph BT
        User[<b>user</b><br /><ul><li>uuid</li><li>username</li><li>display_name</li><li>email</li><li>password</li><li>created_at</li><li>updated_at</li><li>deleted_at</li></ul>]

        Game[<b>game</b><ul><li>uuid</li><li>rawg_id</li><li>slug</li><li>name</li><li>created_at</li><li>updated_at</li><li>deleted_at</li></ul>]

        Save[<b>save</b><ul><li>uuid</li><li>author_uuid</li><li>game_uuid</li><li>title</li><li>description</li><li>download_url</li><li>created_at</li><li>updated_at</li><li>deleted_at</li></ul>]

        SaveUpvote[<b>save_upvote</b><ul><li>user_uuid</li><li>save_uuid</li><li>type</li><li>created_at</li><li>updated_at</li></ul>]

        User <-- 1 - * --> Save
        Game <-- 1 - * --> Save
        User <--- SaveUpvote
        SaveUpvote ---> Save
```

## Installation

### Prerequisites

- **Node.js** and **npm/yarn**
- **Docker**
- **PostgreSQL** and **Redis**
- **Nginx**

### Clone Project

```bash
git clone --recurse-submodules https://github.com/FiestaTheNewbieDev/share-ur-save.git
```

## GitHub Submodules Repositories

- **Backend**: https://github.com/FiestaTheNewbieDev/share-ur-save-backend.git
- **Frontend**: https://github.com/FiestaTheNewbieDev/share-ur-save-frontend.git
