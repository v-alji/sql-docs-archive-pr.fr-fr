---
title: srv_paramsetoutput (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601464"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="87bdd-102">srv_paramsetoutput (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="87bdd-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="87bdd-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="87bdd-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="87bdd-104">Définit la valeur d'un paramètre de retour.</span><span class="sxs-lookup"><span data-stu-id="87bdd-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="87bdd-105">Cette fonction remplace la fonction **srv_paramset**.</span><span class="sxs-lookup"><span data-stu-id="87bdd-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87bdd-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="87bdd-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="87bdd-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="87bdd-107">Arguments</span></span>  
 <span data-ttu-id="87bdd-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="87bdd-108">*srvproc*</span></span>  
 <span data-ttu-id="87bdd-109">Handle d’une connexion cliente.</span><span class="sxs-lookup"><span data-stu-id="87bdd-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="87bdd-110">*n*</span><span class="sxs-lookup"><span data-stu-id="87bdd-110">*n*</span></span>  
 <span data-ttu-id="87bdd-111">Est le nombre ordinal du paramètre à définir.</span><span class="sxs-lookup"><span data-stu-id="87bdd-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="87bdd-112">Le premier paramètre est 1.</span><span class="sxs-lookup"><span data-stu-id="87bdd-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="87bdd-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="87bdd-113">*pbData*</span></span>  
 <span data-ttu-id="87bdd-114">Pointeur vers la valeur de données à renvoyer au client en tant que paramètre de retour de procédure.</span><span class="sxs-lookup"><span data-stu-id="87bdd-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="87bdd-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="87bdd-115">*cbLen*</span></span>  
 <span data-ttu-id="87bdd-116">Est la longueur réelle des données à retourner.</span><span class="sxs-lookup"><span data-stu-id="87bdd-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="87bdd-117">Si le type de données du paramètre spécifie des valeurs de longueur constante et qu’il n’autorise pas les valeurs NULL (par exemple, *srvbit* ou *srvint1*), *cbLen* est ignoré.</span><span class="sxs-lookup"><span data-stu-id="87bdd-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="87bdd-118">La valeur 0 indique des données de longueur nulle si *fNull* a la valeur FALSE.</span><span class="sxs-lookup"><span data-stu-id="87bdd-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="87bdd-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="87bdd-119">*fNull*</span></span>  
 <span data-ttu-id="87bdd-120">Indicateur spécifiant si la valeur du paramètre de retour est NULL.</span><span class="sxs-lookup"><span data-stu-id="87bdd-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="87bdd-121">Attribuez la valeur TRUE à cet indicateur si le paramètre doit avoir la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="87bdd-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="87bdd-122">La valeur par défaut est FALSE.</span><span class="sxs-lookup"><span data-stu-id="87bdd-122">The default value is FALSE.</span></span> <span data-ttu-id="87bdd-123">Si *fNull* a la valeur TRUE, *cbLen* doit avoir la valeur 0, sinon la fonction échoue.</span><span class="sxs-lookup"><span data-stu-id="87bdd-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="87bdd-124">Retours</span><span class="sxs-lookup"><span data-stu-id="87bdd-124">Returns</span></span>  
 <span data-ttu-id="87bdd-125">Si les informations de paramètre ont été définies avec succès, la valeur SUCCEED est retournée ; sinon, la valeur FAIL est retournée.</span><span class="sxs-lookup"><span data-stu-id="87bdd-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="87bdd-126">La valeur FAIL est retournée dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="87bdd-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="87bdd-127">le paramètre n'est pas un paramètre de retour, ou</span><span class="sxs-lookup"><span data-stu-id="87bdd-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="87bdd-128">l’argument *cbLen* n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="87bdd-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87bdd-129">Notes</span><span class="sxs-lookup"><span data-stu-id="87bdd-129">Remarks</span></span>  
 <span data-ttu-id="87bdd-130">**Remarque relative à la sécurité** Il est recommandé de revoir en détail le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="87bdd-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="87bdd-131">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="87bdd-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
