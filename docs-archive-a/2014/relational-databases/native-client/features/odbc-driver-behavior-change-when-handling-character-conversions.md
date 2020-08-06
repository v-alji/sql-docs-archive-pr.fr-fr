---
title: Changement de comportement du pilote ODBC lors de la gestion des conversions de caractères | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698064"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="f70eb-102">Changement de comportement du pilote ODBC lors de la gestion des conversions de caractères</span><span class="sxs-lookup"><span data-stu-id="f70eb-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="f70eb-103">Le [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] pilote ODBC de Native Client (SQLNCLI11.dll) a modifié son mode de conversion de SQL_WCHAR \* (NCHAR/NVARCHAR/nvarchar (max)) et SQL_CHAR \* (char/varchar/NARCHAR (max)).</span><span class="sxs-lookup"><span data-stu-id="f70eb-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="f70eb-104">Les fonctions ODBC, telles que SQLGetData, SQLBindCol et SQLBindParameter, retournent (-4) SQL_NO_TOTAL comme paramètre de longueur/indicateur lors de l'utilisation du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span><span class="sxs-lookup"><span data-stu-id="f70eb-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="f70eb-105">Les versions antérieures du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client retournaient une valeur de longueur, ce qui peut s'avérer incorrect.</span><span class="sxs-lookup"><span data-stu-id="f70eb-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="f70eb-106">Comportement de SQLGetData</span><span class="sxs-lookup"><span data-stu-id="f70eb-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="f70eb-107">La plupart des fonctions Windows vous permettent de spécifier une taille de mémoire tampon de 0, et la longueur retournée correspond à la taille des données renvoyées.</span><span class="sxs-lookup"><span data-stu-id="f70eb-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="f70eb-108">Le motif suivant est bien connu des programmeurs Windows :</span><span class="sxs-lookup"><span data-stu-id="f70eb-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="f70eb-109">Toutefois, **SQLGetData** ne doit pas être utilisé dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="f70eb-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="f70eb-110">Le motif suivant ne doit pas être utilisé :</span><span class="sxs-lookup"><span data-stu-id="f70eb-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="f70eb-111">**SQLGetData** ne peut être appelé que pour récupérer des blocs de données réelles.</span><span class="sxs-lookup"><span data-stu-id="f70eb-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="f70eb-112">L’utilisation de **SQLGetData** pour récupérer la taille des données n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f70eb-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="f70eb-113">Ce qui suit montre l'impact du changement de pilote lors de l'utilisation d'un motif incorrect.</span><span class="sxs-lookup"><span data-stu-id="f70eb-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="f70eb-114">Cette application interroge une colonne `varchar` et une liaison au format Unicode (SQL_UNICODE/SQL_WCHAR) :</span><span class="sxs-lookup"><span data-stu-id="f70eb-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="f70eb-115">Demande`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="f70eb-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|<span data-ttu-id="f70eb-116">Version du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="f70eb-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="f70eb-117">Résultat de longueur ou d'indicateur</span><span class="sxs-lookup"><span data-stu-id="f70eb-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="f70eb-118">Description</span><span class="sxs-lookup"><span data-stu-id="f70eb-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="f70eb-119">Native Client ou antérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-119">Native Client or earlier</span></span>|<span data-ttu-id="f70eb-120">6</span><span class="sxs-lookup"><span data-stu-id="f70eb-120">6</span></span>|<span data-ttu-id="f70eb-121">Le pilote a déduit par erreur que la conversion de CHAR en WCHAR serait obtenue en multipliant la longueur par 2.</span><span class="sxs-lookup"><span data-stu-id="f70eb-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="f70eb-122">Native Client (version 11.0.2100.60) ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-122">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="f70eb-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="f70eb-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="f70eb-124">Le pilote ne suppose plus que la conversion de CHAR en WCHAR ou WCHAR en CHAR est une action (Multiply) \* 2 ou (Division)/2.</span><span class="sxs-lookup"><span data-stu-id="f70eb-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="f70eb-125">L’appel de **SQLGetData** ne retourne plus la longueur de la conversion attendue.</span><span class="sxs-lookup"><span data-stu-id="f70eb-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="f70eb-126">Le pilote détecte la conversion vers ou depuis CHAR et WCHAR, puis retourne (-4) SQL_NO_TOTAL au lieu du comportement \*2 ou /2 qui peut être incorrect.</span><span class="sxs-lookup"><span data-stu-id="f70eb-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="f70eb-127">Utilisez **SQLGetData** pour récupérer les segments des données.</span><span class="sxs-lookup"><span data-stu-id="f70eb-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="f70eb-128">(Pseudo-code illustré :)</span><span class="sxs-lookup"><span data-stu-id="f70eb-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="f70eb-129">Comportement de SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="f70eb-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="f70eb-130">Demande`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="f70eb-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|<span data-ttu-id="f70eb-131">Version du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="f70eb-131">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="f70eb-132">Résultat de longueur ou d'indicateur</span><span class="sxs-lookup"><span data-stu-id="f70eb-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="f70eb-133">Description</span><span class="sxs-lookup"><span data-stu-id="f70eb-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="f70eb-134">Native Client ou antérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-134">Native Client or earlier</span></span>|<span data-ttu-id="f70eb-135">20</span><span class="sxs-lookup"><span data-stu-id="f70eb-135">20</span></span>|<span data-ttu-id="f70eb-136">-   **SQLFetch** signale qu’il existe une troncation à droite des données.</span><span class="sxs-lookup"><span data-stu-id="f70eb-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="f70eb-137">-Length correspond à la longueur des données retournées, pas à celles qui ont été stockées (suppose une conversion \* 2 CHAR en WCHAR qui peut être incorrecte pour les glyphes).</span><span class="sxs-lookup"><span data-stu-id="f70eb-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="f70eb-138">-Les données stockées dans la mémoire tampon sont 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="f70eb-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="f70eb-139">La mémoire tampon est alors certaine de se terminer par une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="f70eb-140">Native Client (version 11.0.2100.60) ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-140">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="f70eb-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="f70eb-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="f70eb-142">-   **SQLFetch** signale qu’il existe une troncation à droite des données.</span><span class="sxs-lookup"><span data-stu-id="f70eb-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="f70eb-143">-Length indique-4 (SQL_NO_TOTAL) parce que le reste des données n’a pas été converti.</span><span class="sxs-lookup"><span data-stu-id="f70eb-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="f70eb-144">-Les données stockées dans la mémoire tampon sont 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="f70eb-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="f70eb-145">- La mémoire tampon est alors certaine de se terminer par une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="f70eb-146">SQLBindParameter (comportement du paramètre OUTPUT)</span><span class="sxs-lookup"><span data-stu-id="f70eb-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="f70eb-147">Demande`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="f70eb-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|<span data-ttu-id="f70eb-148">Version du pilote ODBC [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="f70eb-148">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="f70eb-149">Résultat de longueur ou d'indicateur</span><span class="sxs-lookup"><span data-stu-id="f70eb-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="f70eb-150">Description</span><span class="sxs-lookup"><span data-stu-id="f70eb-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="f70eb-151">Native Client ou antérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-151">Native Client or earlier</span></span>|<span data-ttu-id="f70eb-152">2468</span><span class="sxs-lookup"><span data-stu-id="f70eb-152">2468</span></span>|<span data-ttu-id="f70eb-153">-   **SQLFetch** ne retourne plus de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="f70eb-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="f70eb-154">-   **SQLMoreResults** ne retourne plus de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="f70eb-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="f70eb-155">-Length indique la taille des données retournées par le serveur, et non stockées dans la mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="f70eb-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="f70eb-156">-La mémoire tampon d’origine contient 63 octets et un terminateur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="f70eb-157">La mémoire tampon est alors certaine de se terminer par une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="f70eb-158">Native Client (version 11.0.2100.60) ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="f70eb-158">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="f70eb-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="f70eb-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="f70eb-160">-   **SQLFetch** ne retourne plus de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="f70eb-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="f70eb-161">-   **SQLMoreResults** ne retourne plus de données disponibles.</span><span class="sxs-lookup"><span data-stu-id="f70eb-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="f70eb-162">-Length indique (-4) SQL_NO_TOTAL, car le reste des données n’a pas été converti.</span><span class="sxs-lookup"><span data-stu-id="f70eb-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="f70eb-163">-La mémoire tampon d’origine contient 63 octets et un terminateur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="f70eb-164">La mémoire tampon est alors certaine de se terminer par une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="f70eb-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="f70eb-165">Réalisation de conversions CHAR et WCHAR</span><span class="sxs-lookup"><span data-stu-id="f70eb-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="f70eb-166">Le pilote ODBC [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client propose plusieurs manières d'effectuer des conversions CHAR et WCHAR.</span><span class="sxs-lookup"><span data-stu-id="f70eb-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="f70eb-167">La logique est similaire à la manipulation d’objets BLOB (varchar (max), nvarchar (max),...) :</span><span class="sxs-lookup"><span data-stu-id="f70eb-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="f70eb-168">Les données sont enregistrées ou tronquées dans la mémoire tampon spécifiée lors de la liaison avec **SQLBindCol** ou **SQLBindParameter**.</span><span class="sxs-lookup"><span data-stu-id="f70eb-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="f70eb-169">Si vous n’effectuez pas de liaison, vous pouvez récupérer les données par segments à l’aide de **SQLGetData** et **SQLParamData**.</span><span class="sxs-lookup"><span data-stu-id="f70eb-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70eb-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f70eb-170">See Also</span></span>  
 [<span data-ttu-id="f70eb-171">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f70eb-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
