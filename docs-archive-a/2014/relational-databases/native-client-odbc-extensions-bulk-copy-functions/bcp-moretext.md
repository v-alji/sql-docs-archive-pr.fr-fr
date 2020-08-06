---
title: bcp_moretext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603507"
---
# <a name="bcp_moretext"></a><span data-ttu-id="319c8-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="319c8-102">bcp_moretext</span></span>
  <span data-ttu-id="319c8-103">Envoie une partie d'une valeur de type de données longue et de longueur variable à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="319c8-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="319c8-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="319c8-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="319c8-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="319c8-105">Arguments</span></span>  
 <span data-ttu-id="319c8-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="319c8-106">*hdbc*</span></span>  
 <span data-ttu-id="319c8-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="319c8-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="319c8-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="319c8-108">*cbData*</span></span>  
 <span data-ttu-id="319c8-109">Nombre d’octets de données copiés vers SQL Server à partir des données référencées par *pData*.</span><span class="sxs-lookup"><span data-stu-id="319c8-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="319c8-110">Une valeur de SQL_NULL_DATA indique NULL.</span><span class="sxs-lookup"><span data-stu-id="319c8-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="319c8-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="319c8-111">*pData*</span></span>  
 <span data-ttu-id="319c8-112">Pointeur vers le segment de données long, de longueur variable, pris en charge à envoyer à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="319c8-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="319c8-113">Retours</span><span class="sxs-lookup"><span data-stu-id="319c8-113">Returns</span></span>  
 <span data-ttu-id="319c8-114">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="319c8-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="319c8-115">Notes</span><span class="sxs-lookup"><span data-stu-id="319c8-115">Remarks</span></span>  
 <span data-ttu-id="319c8-116">Cette fonction peut être utilisée conjointement avec des [bcp_bind](bcp-bind.md) et des [bcp_sendrow](bcp-sendrow.md) pour copier des valeurs de données longues de longueur variable en SQL Server dans plusieurs segments plus petits.</span><span class="sxs-lookup"><span data-stu-id="319c8-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="319c8-117">**bcp_moretext** peut être utilisé avec des colonnes qui ont les types de données SQL Server suivants :,,,,, `text` `ntext` , le `image` `varchar(max)` `nvarchar(max)` `varbinary(max)` type défini par l’utilisateur (UDT) et XML.</span><span class="sxs-lookup"><span data-stu-id="319c8-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="319c8-118">**bcp_moretext** ne prend pas en charge les conversions de données, les données fournies doivent correspondre au type de données de la colonne cible.</span><span class="sxs-lookup"><span data-stu-id="319c8-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="319c8-119">Si **bcp_bind** est appelé avec un paramètre *pData* non null pour les types de données pris en charge par **bcp_moretext**, `bcp_sendrow` envoie la valeur de données entière, quelle que soit la longueur.</span><span class="sxs-lookup"><span data-stu-id="319c8-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="319c8-120">Toutefois, si **bcp_bind** possède un paramètre *pData* null pour les types de données pris en charge, **bcp_moretext** peut être utilisé pour copier des données immédiatement après un retour réussi de `bcp_sendrow` indiquant que toutes les colonnes liées avec des données présentes ont été traitées.</span><span class="sxs-lookup"><span data-stu-id="319c8-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="319c8-121">Si vous utilisez **bcp_moretext** pour envoyer une colonne de type de données prise en charge dans une ligne, vous devez également l’utiliser pour envoyer toutes les autres colonnes de type de données prises en charge dans la ligne.</span><span class="sxs-lookup"><span data-stu-id="319c8-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="319c8-122">Aucune colonne ne peut être ignorée.</span><span class="sxs-lookup"><span data-stu-id="319c8-122">No columns may be skipped.</span></span> <span data-ttu-id="319c8-123">Les types de données pris en charge sont SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT et SQLXML.</span><span class="sxs-lookup"><span data-stu-id="319c8-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="319c8-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY et SQLVARBINARY appartiennent également à cette catégorie si la colonne est un varchar (max), nvarchar (max) ou varbinary (max), respectivement.</span><span class="sxs-lookup"><span data-stu-id="319c8-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="319c8-125">L’appel de **bcp_bind** ou [bcp_collen](bcp-collen.md) définit la longueur totale de toutes les parties de données à copier dans la colonne SQL Server.</span><span class="sxs-lookup"><span data-stu-id="319c8-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="319c8-126">Une tentative d’envoi d’SQL Server plus d’octets que ce qui est spécifié dans l’appel à **bcp_bind** ou `bcp_collen` génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="319c8-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="319c8-127">Cette erreur se produit, par exemple, dans une application qui `bcp_collen` a utilisé pour définir la longueur des données disponibles pour une `text` colonne SQL Server sur 4500, puis appelée **bcp_moretext** cinq fois en indiquant à chaque appel que la longueur de la mémoire tampon de données était de 1000 octets.</span><span class="sxs-lookup"><span data-stu-id="319c8-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="319c8-128">Si une ligne copiée contient plus d’une colonne de longueur variable, **bcp_moretext** envoie tout d’abord ses données à la colonne à numérotation ordinale la plus basse, suivie de la colonne numérotée ordinale suivante, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="319c8-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="319c8-129">Il est important de définir correctement la longueur totale des données attendues.</span><span class="sxs-lookup"><span data-stu-id="319c8-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="319c8-130">Il n'existe aucun moyen de signaler, en dehors du paramètre de longueur, que toutes les données pour une colonne ont été reçues par copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="319c8-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="319c8-131">Lorsque `var(max)` des valeurs sont envoyées au serveur à l’aide de bcp_sendrow et bcp_moretext, il n’est pas nécessaire d’appeler bcp_collen pour définir la longueur de la colonne.</span><span class="sxs-lookup"><span data-stu-id="319c8-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="319c8-132">Au lieu de cela, pour ces types uniquement, la valeur se termine en appelant bcp_sendrow avec une longueur de zéro.</span><span class="sxs-lookup"><span data-stu-id="319c8-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="319c8-133">Une application appelle normalement `bcp_sendrow` et **bcp_moretext** dans des boucles pour envoyer un certain nombre de lignes de données.</span><span class="sxs-lookup"><span data-stu-id="319c8-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="319c8-134">Voici un aperçu de la procédure à suivre pour une table contenant deux `text` colonnes :</span><span class="sxs-lookup"><span data-stu-id="319c8-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="319c8-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="319c8-135">Example</span></span>  
 <span data-ttu-id="319c8-136">Cet exemple montre comment utiliser **bcp_moretext** avec **bcp_bind** et `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="319c8-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="319c8-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="319c8-137">See Also</span></span>  
 [<span data-ttu-id="319c8-138">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="319c8-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
