---
title: srv_describe (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614065"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="9f9d8-102">srv_describe (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="9f9d8-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9f9d8-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9f9d8-104">Définit le nom de colonne et les types de données sources et de destination pour une colonne spécifique.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f9d8-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9f9d8-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f9d8-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="9f9d8-106">Arguments</span></span>  
 <span data-ttu-id="9f9d8-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-107">*srvproc*</span></span>  
 <span data-ttu-id="9f9d8-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le client qui envoie la ligne).</span><span class="sxs-lookup"><span data-stu-id="9f9d8-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="9f9d8-109">La structure contient toutes les informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="9f9d8-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-110">*colnumber*</span></span>  
 <span data-ttu-id="9f9d8-111">N’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-111">Is currently not supported.</span></span> <span data-ttu-id="9f9d8-112">Les colonnes doivent être décrites dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-112">Columns must be described in order.</span></span> <span data-ttu-id="9f9d8-113">Toutes les colonnes doivent être décrites avant que **srv_sendrow** ne soit appelé.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="9f9d8-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-114">*column_name*</span></span>  
 <span data-ttu-id="9f9d8-115">Spécifie le nom de la colonne à laquelle les données appartiennent.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="9f9d8-116">Ce paramètre peut être NULL car il n'est pas obligatoire qu'une colonne ait un nom.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="9f9d8-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-117">*namelen*</span></span>  
 <span data-ttu-id="9f9d8-118">Spécifie la longueur, en octets, de *column_name*.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="9f9d8-119">Si *namelen* est SRV_NULLTERM, *column_name* doit se terminer par null.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="9f9d8-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-120">*desttype*</span></span>  
 <span data-ttu-id="9f9d8-121">Spécifie le type de données de la colonne de ligne de destination.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="9f9d8-122">Il s'agit du type de données envoyé au client.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-122">This is the data type sent to the client.</span></span> <span data-ttu-id="9f9d8-123">Le type de données doit être spécifié même si les données sont NULL. Pour plus d’informations, consultez [Types de données &#40;API de procédure stockée étendue&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="9f9d8-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="9f9d8-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-124">*destlen*</span></span>  
 <span data-ttu-id="9f9d8-125">Spécifie la longueur, en octets, des données à envoyer au client.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="9f9d8-126">Pour les types de données de longueur fixe qui n’autorisent pas de valeurs NULL, *destlen* est ignoré.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="9f9d8-127">Pour les types de données de longueur variable et les types de données de longueur fixe qui autorisent les valeurs NULL, *destlen* spécifie la longueur maximale des données de destination.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="9f9d8-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-128">*srctype*</span></span>  
 <span data-ttu-id="9f9d8-129">Spécifie le type de données des données sources.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="9f9d8-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-130">*srclen*</span></span>  
 <span data-ttu-id="9f9d8-131">Spécifie la longueur, en octets, des données sources.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="9f9d8-132">Cette valeur est ignorée pour les types de données de longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="9f9d8-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="9f9d8-133">*srcdata*</span></span>  
 <span data-ttu-id="9f9d8-134">Fournit l'adresse des données sources pour une colonne particulière.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="9f9d8-135">Quand **srv_sendrow** est appelé, il recherche les données pour *colnumber* à *srcdata*.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="9f9d8-136">Ainsi, il ne doit pas être libéré avant un appel à **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="9f9d8-137">Vous pouvez changer l’adresse des données sources entre des appels à **srv_sendrow** à l’aide de **srv_setcoldata**.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="9f9d8-138">La mémoire allouée pour *srcdata* ne doit pas être libérée tant que les données de la colonne ne sont pas remplacées par un autre appel à **srv_setcoldata** ou tant que **srv_senddone** n’est pas appelé.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="9f9d8-139">Si *desttype* est SRVDECIMAL ou SRVNUMERIC, le paramètre *srcdata* doit être un pointeur vers une structure DBNUMERIC ou DBDECIMAL avec les champs de précision et d’échelle de la structure déjà définis aux valeurs que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="9f9d8-140">Vous pouvez utiliser DEFAULTPRECISION pour spécifier une précision par défaut et DEFAULTSCALE pour spécifier une échelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9f9d8-141">Retours</span><span class="sxs-lookup"><span data-stu-id="9f9d8-141">Returns</span></span>  
 <span data-ttu-id="9f9d8-142">Numéro de la colonne décrite.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-142">The number of the column described.</span></span> <span data-ttu-id="9f9d8-143">La première colonne est la colonne 1.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-143">The first column is column 1.</span></span> <span data-ttu-id="9f9d8-144">Si une erreur se produit, retourne 0.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f9d8-145">Notes</span><span class="sxs-lookup"><span data-stu-id="9f9d8-145">Remarks</span></span>  
 <span data-ttu-id="9f9d8-146">La fonction **srv_describe** doit être appelée une fois pour chaque colonne dans la ligne avant le premier appel à **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="9f9d8-147">Les colonnes d'une ligne peuvent être décrites dans n'importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="9f9d8-148">Pour changer l’emplacement et la longueur des données sources dans les lignes de colonnes avant d’envoyer le jeu de résultats complet, utilisez **srv_setcoldata** et **srv_setcollen**, respectivement.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="9f9d8-149">Pour une description des types de données et des conversions de types de données d’API de procédure stockée étendue, consultez [Types de données &#40;API de procédure stockée étendue&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="9f9d8-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="9f9d8-150">Si le nom de colonne dans votre application est en Unicode, vous devez le convertir en page de codes multioctets du serveur avant d’appeler **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="9f9d8-151">Pour plus d’informations, consultez [données Unicode et pages de codes du serveur](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="9f9d8-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f9d8-152">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="9f9d8-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9f9d8-153">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9f9d8-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9d8-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f9d8-154">See Also</span></span>  
 <span data-ttu-id="9f9d8-155">[srv_sendrow &#40;API de procédure stockée étendue&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="9f9d8-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="9f9d8-156">[srv_setutype &#40;API de procédure stockée étendue&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="9f9d8-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="9f9d8-157">srv_setcoldata &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="9f9d8-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
