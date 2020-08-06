---
title: srv_setutype (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707564"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="ee932-102">srv_setutype (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="ee932-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ee932-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="ee932-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ee932-104">Définit le type de données défini par l'utilisateur pour la colonne d'une ligne.</span><span class="sxs-lookup"><span data-stu-id="ee932-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee932-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ee932-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ee932-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="ee932-106">Arguments</span></span>  
 <span data-ttu-id="ee932-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ee932-107">*srvproc*</span></span>  
 <span data-ttu-id="ee932-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="ee932-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="ee932-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="ee932-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="ee932-110">*column*</span><span class="sxs-lookup"><span data-stu-id="ee932-110">*column*</span></span>  
 <span data-ttu-id="ee932-111">Indique quelle est la colonne à définir.</span><span class="sxs-lookup"><span data-stu-id="ee932-111">Indicates which column to set.</span></span> <span data-ttu-id="ee932-112">Les colonnes sont numérotées, en commençant par 1.</span><span class="sxs-lookup"><span data-stu-id="ee932-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="ee932-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="ee932-113">*user_type*</span></span>  
 <span data-ttu-id="ee932-114">Spécifie le code de type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee932-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ee932-115">Retours</span><span class="sxs-lookup"><span data-stu-id="ee932-115">Returns</span></span>  
 <span data-ttu-id="ee932-116">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="ee932-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="ee932-117">Retourne FAIL si la colonne n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="ee932-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee932-118">Notes</span><span class="sxs-lookup"><span data-stu-id="ee932-118">Remarks</span></span>  
 <span data-ttu-id="ee932-119">Une colonne a deux types de données : son type de données réel et son type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ee932-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="ee932-120">Le type de données défini par l’utilisateur est utilisé par [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour stocker le type de données défini par l’utilisateur réel de la colonne, le cas échéant, et les informations de description de la colonne, telles que la possibilité de valeur null et la possibilité de mise à jour, pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="ee932-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="ee932-121">La fonction **srv_setutype** peut être appelée chaque fois que *column* a été défini avec **srv_describe** et avant que la dernière ligne n’ait été envoyée.</span><span class="sxs-lookup"><span data-stu-id="ee932-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ee932-122">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="ee932-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ee932-123">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ee932-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee932-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee932-124">See Also</span></span>  
 [<span data-ttu-id="ee932-125">srv_describe &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="ee932-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
