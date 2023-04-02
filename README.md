# To do list Database

## Database diagram

![image](https://user-images.githubusercontent.com/106080433/229336758-b944a712-8d9f-4bec-b552-ce2c3d474c5b.png)

## Database Script

### Category

```
CREATE TABLE Category(
"id" INT IDENTITY NOT NULL,
"name" VARCHAR(55) NOT NULL,
CONSTRAINT PK_Category PRIMARY KEY ("id")
);
```

### Deal

```
CREATE TABLE Deal(
"id" INT IDENTITY NOT NULL,
"name" VARCHAR(55) NOT NULL,
"isComplete" BIT DEFAULT 0 NOT NULL,
"dueDate" DATE,
"task" VARCHAR(MAX),
CONSTRAINT PK_Deal PRIMARY KEY ("id")
);
```

### DealCategory

```
CREATE TABLE DealCategory(
"id_deal" INT  NOT NULL,
"id_category" INT  NOT NULL,
CONSTRAINT FK_Id_Deal FOREIGN KEY("id_deal") REFERENCES Deal("id") ON DELETE CASCADE,
CONSTRAINT FK_Id_Category FOREIGN KEY("id_category") REFERENCES Category("id") ON DELETE CASCADE,
CONSTRAINT PK_Id_DealCategory PRIMARY KEY("id_deal","id_category")
);
```
