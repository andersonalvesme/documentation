---
description: Framework ORM
---

# Prisma

install: **yarn add prisma**

create migrations: **yarn add @prisma/client**

Inicializar: **npx prisma init**

****

Create migrations, example:

```javascript
model User {
    id Int @id @default(autoincrement())
    name String
    email String
    password String
    created_at DateTime? @default(now())
    updated_at DateTime? @default(now())

    @@map("users")
}
```

For create use the command: **yarn prisma migrate dev**
