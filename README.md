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

## Architecture
```mermaid
    graph BT
        subgraph Frond-End[<b>Front-End</b>]
            Website[<b>Website</b><br /><ul><li><i>Next.js</i></li><li><i>Redux</i></li></ul>]
        end
        subgraph Back-End[<b>Back-End</b>]
            API[<b>API</b><br /><ul><li><i>NestJS</i></li><li><i>Express</i></li><li><i>Prisma</i></li></ul>]
            Redis[<b>Redis</b>]
            DB[<b>DB</b><br /><ul><li><i>PostgreSQL</i></li></ul>]
            API <--> Redis
            API <--> DB
        end
    API <-- HTTP/HTTPS --> Website
```

## Installation

### Prerequisites

- **Node.js** and **npm/yarn**
- **Docker**
- **PostgreSQL** and **Redis**

### Clone Project

```bash
git clone --recurse-submodules https://github.com/FiestaTheNewbieDev/share-ur-save.git
```

## GitHub Submodules Repositories

- **Backend**: https://github.com/FiestaTheNewbieDev/share-ur-save-backend.git
- **Frontend**: https://github.com/FiestaTheNewbieDev/share-ur-save-frontend.git