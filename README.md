Prestige
========
ALTER PROCEDURE [dbo].[Prestigie]
	@lg [nvarchar](20)
AS
DECLARE @in int, @fn int, @level int, @prestlevel int

SET @in = 0
SET @fn = 0
WHILE @in < 9
BEGIN
SET @level = (SELECT Level FROM [dbo].[Characters] WHERE Login = @lg AND CharType = @in)
SET @prestlevel = (SELECT PrestigieLevel FROM [dbo].[Prestigies] WHERE Login = @lg)
IF @level >= 75
BEGIN
IF @fn = 8
BEGIN
IF NOT @prestlevel = 10
BEGIN
SET @prestlevel = (@prestlevel+1)
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 0
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 1
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 2
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 3
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 4
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 5
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 6
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 7
UPDATE [dbo].[Characters] SET Level='0', Exp='0' WHERE Login = @lg AND CharType = 8
UPDATE [dbo].[Prestigies] SET PrestigieLevel=@prestlevel WHERE Login = @lg
IF @prestlevel = 1
BEGIN 
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 2
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 3
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 4
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 5
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 6
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 7
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='1ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 8
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 9
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END ELSE IF @prestlevel = 10
BEGIN
UPDATE [dbo].[GoodsObjectList] WITH(updlock) SET ItemID='ID ITEM VaI RECEBER' WHERE OwnerLogin=@lg AND ItemID='ID ITEM que detecta se existe'
END
END
END
SET @fn = (@fn+1)
END
SET @in = (@in+1)
END
