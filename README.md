# Proyecto_SIG
Desarrollo de SIG par BodyBoost
Create    DATABASE Bodyboost;
USE Bodyboost;
CREATE TABLE CLIENTE (
        CLIENTE_ID varchar(30) PRIMARY KEY,
        NOMBRE VARCHAR(20),
        EMAIL VARCHAR (40),
        TELEFONO INT,
        DIRECCION VARCHAR(40),
        CIUDAD VARCHAR (10)
);
CREATE TABLE DESCUENTOS_ACTIVOS (
         CODIGO_DESCUENTO VARCHAR(15) PRIMARY KEY,
         DESCUENTO INT
);
CREATE TABLE ORDEN (
        ORDEN_ID INT,
        ORDEN_SHOPIFY varchar(20)  PRIMARY KEY,
        CLIENTE_ID varchar(30),
        FECHA DATE,
        SUBTOTAL INT,
        ESTADO VARCHAR(20),
        METODO_ENTREGA VARCHAR(45),
        TAXES INT,
        CODIGO_DESCUENTO int,
        TOTAL INT,
        METODO_PAGO VARCHAR(45),
        MARKETING VARCHAR(45)
        );
CREATE TABLE PRODUCTO (
        PRODUCTO_ID INT PRIMARY KEY,
        NOMBRE VARCHAR(20),
        PRECIO INT,
        PRECIO_PROV INT,
        STOCK INT
);
create table stock (
        producto varchar(50) primary key,
        stock int
);
Create table producto_cliente_orden
(Order_ID INT primary key, 
Producto_ID int,
Cliente_ID varchar(30),
Cantidad_producto int,
foreign key (Order_ID) references Orden (Orden_ID),
foreign key (Producto_ID) references producto(Producto_ID),
foreign key (Cliente_ID) references cliente (Cliente_ID));
