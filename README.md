# To do list Database

## Database diagram

![image](https://user-images.githubusercontent.com/106080433/229533645-58bcc149-4d14-483a-889e-573efeb9f047.png)

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
"category_id" INT NOT NULL,
"name" NVARCHAR(55) NOT NULL,
"is_complete" BIT DEFAULT 0 NOT NULL,
"due_date" DATE,
CONSTRAINT FK_DealCategory_CategoryId FOREIGN KEY("category_id") REFERENCES Category("id") ON DELETE CASCADE,
CONSTRAINT PK_Deal PRIMARY KEY ("id")
);
```
