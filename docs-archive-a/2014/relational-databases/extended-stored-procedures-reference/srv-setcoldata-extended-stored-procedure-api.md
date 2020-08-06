---
title: srv_setcoldata (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707567"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="e380d-102">srv_setcoldata (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="e380d-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="e380d-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="e380d-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="e380d-104">Spécifie l'adresse actuelle pour les données d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="e380d-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e380d-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e380d-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e380d-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="e380d-106">Arguments</span></span>  
 <span data-ttu-id="e380d-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="e380d-107">*srvproc*</span></span>  
 <span data-ttu-id="e380d-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="e380d-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="e380d-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="e380d-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="e380d-110">*column*</span><span class="sxs-lookup"><span data-stu-id="e380d-110">*column*</span></span>  
 <span data-ttu-id="e380d-111">Indique le numéro de la colonne pour laquelle l'adresse est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e380d-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="e380d-112">Les colonnes sont numérotées, en commençant par 1.</span><span class="sxs-lookup"><span data-stu-id="e380d-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="e380d-113">*data*</span><span class="sxs-lookup"><span data-stu-id="e380d-113">*data*</span></span>  
 <span data-ttu-id="e380d-114">Pointeur pour les données d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="e380d-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="e380d-115">La mémoire allouée pour *data* ne doit pas être libérée tant que les données de la colonne ne sont pas remplacées par un autre appel à **srv_setcoldata**ou tant que **srv_senddone** n'est pas appelé.</span><span class="sxs-lookup"><span data-stu-id="e380d-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e380d-116">Retours</span><span class="sxs-lookup"><span data-stu-id="e380d-116">Returns</span></span>  
 <span data-ttu-id="e380d-117">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="e380d-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e380d-118">Notes</span><span class="sxs-lookup"><span data-stu-id="e380d-118">Remarks</span></span>  
 <span data-ttu-id="e380d-119">Chaque colonne de la ligne doit être au préalable définie avec **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="e380d-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="e380d-120">Les adresses des données de colonne sont définies initialement avec **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="e380d-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="e380d-121">En cas de modification de l'adresse des données de colonne, **srv_setcoldata** doit être appelé pour spécifier la nouvelle adresse des données et **srv_setcoldata** doit être appelé séparément pour chaque colonne modifiée.</span><span class="sxs-lookup"><span data-stu-id="e380d-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="e380d-122">Pour représenter des données Null, attribuez la valeur 0 à la longueur de la colonne avec **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="e380d-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="e380d-123">L'adresse des données est alors ignorée.</span><span class="sxs-lookup"><span data-stu-id="e380d-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e380d-124">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="e380d-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="e380d-125">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="e380d-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e380d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e380d-126">See Also</span></span>  
 [<span data-ttu-id="e380d-127">srv_describe &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="e380d-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
