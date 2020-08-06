---
title: srv_convert (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614066"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="e4113-102">srv_convert (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="e4113-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="e4113-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="e4113-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="e4113-104">Modifie des données d'un type de données en un autre.</span><span class="sxs-lookup"><span data-stu-id="e4113-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4113-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e4113-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4113-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e4113-106">Arguments</span></span>  
 <span data-ttu-id="e4113-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="e4113-107">*srvproc*</span></span>  
 <span data-ttu-id="e4113-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="e4113-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="e4113-109">La structure contient toutes les informations de contrôle que l'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="e4113-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="e4113-110">Si le handle *srvproc* est fourni, il est passé à la fonction du gestionnaire d’erreurs d’API de procédure stockée étendue quand une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="e4113-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="e4113-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="e4113-111">*srctype*</span></span>  
 <span data-ttu-id="e4113-112">Spécifie le type des données à convertir.</span><span class="sxs-lookup"><span data-stu-id="e4113-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="e4113-113">Ce paramètre peut être n'importe lequel des types de données d'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="e4113-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="e4113-114">*src*</span><span class="sxs-lookup"><span data-stu-id="e4113-114">*src*</span></span>  
 <span data-ttu-id="e4113-115">Pointeur vers les données à convertir.</span><span class="sxs-lookup"><span data-stu-id="e4113-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="e4113-116">Ce paramètre peut être n'importe lequel des types de données d'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="e4113-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="e4113-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="e4113-117">*srclen*</span></span>  
 <span data-ttu-id="e4113-118">Spécifie la longueur, en octets, des données à convertir.</span><span class="sxs-lookup"><span data-stu-id="e4113-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="e4113-119">Si *srclen* est 0, **srv_convert** place une valeur NULL dans la variable de destination.</span><span class="sxs-lookup"><span data-stu-id="e4113-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="e4113-120">À moins d'être égal à 0, ce paramètre est ignoré pour les types de données de longueur fixe, auquel cas les données sources sont supposées être NULL.</span><span class="sxs-lookup"><span data-stu-id="e4113-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="e4113-121">Pour les données du type de données SRVCHAR, une longueur de -1 indique que la chaîne se termine par NULL.</span><span class="sxs-lookup"><span data-stu-id="e4113-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="e4113-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="e4113-122">*desttype*</span></span>  
 <span data-ttu-id="e4113-123">Spécifie le type de données vers lequel convertir la source.</span><span class="sxs-lookup"><span data-stu-id="e4113-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="e4113-124">Ce paramètre peut être n'importe lequel des types de données d'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="e4113-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="e4113-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="e4113-125">*dest*</span></span>  
 <span data-ttu-id="e4113-126">Pointeur vers la variable de destination qui reçoit les données converties.</span><span class="sxs-lookup"><span data-stu-id="e4113-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="e4113-127">Si ce pointeur est NULL, **srv_convert** appelle le gestionnaire d’erreurs fourni par l’utilisateur, le cas échéant, et retourne -1.</span><span class="sxs-lookup"><span data-stu-id="e4113-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="e4113-128">Si *desttype* est SRVDECIMAL ou SRVNUMERIC, le paramètre *dest* doit être un pointeur vers une structure DBNUMERIC ou DBDECIMAL avec les champs de précision et d’échelle de la structure déjà définis aux valeurs souhaitées.</span><span class="sxs-lookup"><span data-stu-id="e4113-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="e4113-129">Vous pouvez utiliser DEFAULTPRECISION pour spécifier une précision par défaut et DEFAULTSCALE pour spécifier une échelle par défaut.</span><span class="sxs-lookup"><span data-stu-id="e4113-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="e4113-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="e4113-130">*destlen*</span></span>  
 <span data-ttu-id="e4113-131">Spécifie la longueur, en octets, de la variable de destination.</span><span class="sxs-lookup"><span data-stu-id="e4113-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="e4113-132">Ce paramètre est ignoré pour les types de données de longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="e4113-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="e4113-133">Pour une variable de destination de type SRVCHAR, la valeur de *destlen* doit être la longueur totale de l’espace de mémoire tampon de destination.</span><span class="sxs-lookup"><span data-stu-id="e4113-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="e4113-134">Une longueur de -1 pour une variable de destination de type SRVCHAR ou SRVBINARY indique que l'espace disponible est suffisant.</span><span class="sxs-lookup"><span data-stu-id="e4113-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="e4113-135">Pour une variable de destination de type *srvchar*, une longueur de -1 fait en sorte que la chaîne de caractères se termine par NULL.</span><span class="sxs-lookup"><span data-stu-id="e4113-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e4113-136">Retours</span><span class="sxs-lookup"><span data-stu-id="e4113-136">Returns</span></span>  
 <span data-ttu-id="e4113-137">Longueur des données converties, en octets, si la conversion de type de données réussit.</span><span class="sxs-lookup"><span data-stu-id="e4113-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="e4113-138">Quand **srv_convert** rencontre une demande de conversion qu’il ne prend pas en charge, il appelle le gestionnaire d’erreurs fourni par le développeur, le cas échéant, définit un numéro d’erreur global et retourne -1.</span><span class="sxs-lookup"><span data-stu-id="e4113-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4113-139">Notes</span><span class="sxs-lookup"><span data-stu-id="e4113-139">Remarks</span></span>  
 <span data-ttu-id="e4113-140">La fonction **srv_willconvert** détermine si une conversion particulière est autorisée.</span><span class="sxs-lookup"><span data-stu-id="e4113-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="e4113-141">La conversion vers le type de données numérique approximatif SRVFLT4 ou SRVFLT8 peut provoquer une certaine perte de précision.</span><span class="sxs-lookup"><span data-stu-id="e4113-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="e4113-142">La conversion à partir du type de données numérique approximatif SRVFLT4 ou SRVFLT8 vers SRVCHAR ou SRVTEXT peut également provoquer une certaine perte de précision.</span><span class="sxs-lookup"><span data-stu-id="e4113-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="e4113-143">La conversion vers SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL ou SRVNUMERIC peut provoquer un dépassement de capacité si le nombre est supérieur à la valeur maximale de la destination ou un dépassement de précision si le nombre est inférieur à la valeur minimale de la destination.</span><span class="sxs-lookup"><span data-stu-id="e4113-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="e4113-144">Si le dépassement de capacité se produit lors de la conversion vers SRVCHAR ou SRVTEXT, le premier caractère de la valeur résultante contient un astérisque (\*) pour indiquer l'erreur.</span><span class="sxs-lookup"><span data-stu-id="e4113-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="e4113-145">Pendant la conversion de SRVCHAR en SRVBINARY, **srv_convert** interprète SRVCHAR comme hexadécimal, que la chaîne contienne ou non un 0 de début.</span><span class="sxs-lookup"><span data-stu-id="e4113-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="e4113-146">Pendant la conversion de SRVBINARY en SRVCHAR, **srv_convert** crée une chaîne hexadécimale sans 0 de début.</span><span class="sxs-lookup"><span data-stu-id="e4113-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="e4113-147">Dans tous les autres cas, une conversion vers ou à partir du type de données SRVBINARY est une copie binaire simple.</span><span class="sxs-lookup"><span data-stu-id="e4113-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="e4113-148">Dans certains cas, il peut être utile de convertir un type de données en lui-même.</span><span class="sxs-lookup"><span data-stu-id="e4113-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="e4113-149">Par exemple, la conversion de SRVCHAR en SRVCHAR avec un *destlen* de -1 ajoute un terminateur NULL à une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e4113-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="e4113-150">Pour une description des types de données et des conversions de types de données d’API de procédure stockée étendue, consultez [Types de données &#40;API de procédure stockée étendue&#41;](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="e4113-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="e4113-151">La fonction **srv_convert** peut échouer pour plusieurs raisons :</span><span class="sxs-lookup"><span data-stu-id="e4113-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="e4113-152">La conversion demandée n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e4113-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="e4113-153">La conversion a provoqué une troncation, un dépassement de capacité ou une perte de précision dans la variable de destination.</span><span class="sxs-lookup"><span data-stu-id="e4113-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="e4113-154">Une erreur de syntaxe s'est produite lors de la conversion d'une chaîne de caractères en un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="e4113-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e4113-155">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="e4113-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="e4113-156">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="e4113-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4113-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4113-157">See Also</span></span>  
 <span data-ttu-id="e4113-158">[srv_setutype &#40;API de procédure stockée étendue&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="e4113-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="e4113-159">srv_willconvert &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="e4113-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
