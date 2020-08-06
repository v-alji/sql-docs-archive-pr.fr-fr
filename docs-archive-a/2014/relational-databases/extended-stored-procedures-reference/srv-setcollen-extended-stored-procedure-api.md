---
title: srv_setcollen (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e3023e2ac239e074656329da7d8af3aba3afa88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698214"
---
# <a name="srv_setcollen-extended-stored-procedure-api"></a><span data-ttu-id="acaa0-102">srv_setcollen (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="acaa0-102">srv_setcollen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="acaa0-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="acaa0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="acaa0-104">Spécifie la longueur de données actuelle, en octets, d'une colonne de longueur variable ou d'une colonne qui autorise des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="acaa0-104">Specifies the current data length in bytes of a variable-length column or a column that allows NULL values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acaa0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="acaa0-105">Syntax</span></span>  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="acaa0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="acaa0-106">Arguments</span></span>  
 <span data-ttu-id="acaa0-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="acaa0-107">*srvproc*</span></span>  
 <span data-ttu-id="acaa0-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="acaa0-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="acaa0-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="acaa0-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="acaa0-110">*column*</span><span class="sxs-lookup"><span data-stu-id="acaa0-110">*column*</span></span>  
 <span data-ttu-id="acaa0-111">Indique le numéro de la colonne pour laquelle la longueur des données est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="acaa0-111">Indicates the number of the column for which the data length is being specified.</span></span> <span data-ttu-id="acaa0-112">Les colonnes sont numérotées, en commençant par 1.</span><span class="sxs-lookup"><span data-stu-id="acaa0-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="acaa0-113">*Len*</span><span class="sxs-lookup"><span data-stu-id="acaa0-113">*len*</span></span>  
 <span data-ttu-id="acaa0-114">Indique la longueur, en octets, des données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="acaa0-114">Indicates the length, in bytes, of the column data.</span></span> <span data-ttu-id="acaa0-115">Une longueur de 0 signifie que les données de la colonne sont Null.</span><span class="sxs-lookup"><span data-stu-id="acaa0-115">A length of 0 means the column data value is null.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="acaa0-116">Retours</span><span class="sxs-lookup"><span data-stu-id="acaa0-116">Returns</span></span>  
 <span data-ttu-id="acaa0-117">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="acaa0-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acaa0-118">Notes</span><span class="sxs-lookup"><span data-stu-id="acaa0-118">Remarks</span></span>  
 <span data-ttu-id="acaa0-119">Chaque colonne de la ligne doit être au préalable définie avec **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="acaa0-119">Each column of the row must first be defined with **srv_describe**.</span></span> <span data-ttu-id="acaa0-120">La longueur des données de la colonne est définie par le dernier appel à **srv_describe** ou **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="acaa0-120">The column data length is set by the last call to **srv_describe** or **srv_setcollen**.</span></span> <span data-ttu-id="acaa0-121">En cas de modification des données de longueur variable (données se terminant par le caractère Null) pour une ligne, vous devez utiliser **srv_setcollen** pour définir la nouvelle longueur avant d’appeler **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="acaa0-121">If variable-length data (null-terminated data) changes for a row, **srv_setcollen** must be used to set it to the new length before calling **srv_sendrow**.</span></span> <span data-ttu-id="acaa0-122">Pour une colonne qui autorise des valeurs Null, **srv_describe** doit être appelé avec un type de données qui autorise des valeurs Null attribué à *desttype* (comme SRVINTN) et des données Null sont spécifiées en appelant **srv_setcollen** avec la valeur 0 attribuée à *len*.</span><span class="sxs-lookup"><span data-stu-id="acaa0-122">For a column that allows null values, **srv_describe** must have been called with *desttype* set to a data type that allows nulls (like SRVINTN) and null data is specified by calling **srv_setcollen** with *len* set to 0.</span></span> <span data-ttu-id="acaa0-123">Les données de longueur nulle ne peuvent pas être spécifiées à l'aide de l'API de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="acaa0-123">Zero length data cannot be specified using the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="acaa0-124">Notez que quand le type de données de la colonne est de longueur variable, *len* n’est pas vérifié.</span><span class="sxs-lookup"><span data-stu-id="acaa0-124">Note that when the data type of the column is variable-length, *len* is not checked.</span></span> <span data-ttu-id="acaa0-125">Cette fonction retourne FAIL si elle est appelée pour une colonne de longueur fixe.</span><span class="sxs-lookup"><span data-stu-id="acaa0-125">This function returns FAIL if called for a fixed-length column.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="acaa0-126">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="acaa0-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="acaa0-127">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="acaa0-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acaa0-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="acaa0-128">See Also</span></span>  
 [<span data-ttu-id="acaa0-129">srv_describe &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="acaa0-129">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
