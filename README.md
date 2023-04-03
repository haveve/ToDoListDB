# To do list Database

## Database diagram

![image](https://user-images.githubusercontent.com/106080433/229347150-4737beed-b1f1-4eb8-851d-ed4dada6b7f9.png)

## Database Script

### Category

```
CREATE TABLE Category(
"id" INT IDENTITY NOT NULL,
"name" NVARCHAR(55) NOT NULL,
CONSTRAINT PK_Category PRIMARY KEY ("id")
);
```

### Deal

```
CREATE TABLE Deal(
"id" INT IDENTITY NOT NULL,
"id_category" INT NOT NULL,
"name" NVARCHAR(55) NOT NULL,
"isComplete" BIT DEFAULT 0 NOT NULL,
"dueDate" DATE,
CONSTRAINT FK_DealCategory_CategoryId FOREIGN KEY("id_category") REFERENCES Category("id") ON DELETE CASCADE,
CONSTRAINT PK_Deal PRIMARY KEY ("id")
);
```
