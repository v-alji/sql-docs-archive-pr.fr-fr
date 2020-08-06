---
title: srv_rpcname (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709476"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="d19c8-102">srv_rpcname (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="d19c8-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d19c8-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="d19c8-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d19c8-104">Retourne le composant de nom de procédure pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="d19c8-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d19c8-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d19c8-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d19c8-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="d19c8-106">Arguments</span></span>  
 <span data-ttu-id="d19c8-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d19c8-107">*srvproc*</span></span>  
 <span data-ttu-id="d19c8-108">Pointeur vers la structure SRV_PROC qui est le handle d'une connexion cliente particulière (dans ce cas, le handle qui a reçu la procédure stockée distante).</span><span class="sxs-lookup"><span data-stu-id="d19c8-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="d19c8-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="d19c8-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="d19c8-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="d19c8-110">*len*</span></span>  
 <span data-ttu-id="d19c8-111">Pointeur vers une variable de type entier qui reçoit la longueur du nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d19c8-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="d19c8-112">Si *len* est NULL, la longueur du nom de procédure stockée distante n'est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="d19c8-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d19c8-113">Retours</span><span class="sxs-lookup"><span data-stu-id="d19c8-113">Returns</span></span>  
 <span data-ttu-id="d19c8-114">Un pointeur DBCHAR vers la chaîne terminée par le caractère NULL pour le composant de nom de procédure stockée distante de la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="d19c8-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="d19c8-115">S'il n'y a pas de procédure stockée distante actuelle, NULL est retourné et *len* est défini à -1.</span><span class="sxs-lookup"><span data-stu-id="d19c8-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d19c8-116">Notes</span><span class="sxs-lookup"><span data-stu-id="d19c8-116">Remarks</span></span>  
 <span data-ttu-id="d19c8-117">Cette fonction retourne uniquement le nom de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="d19c8-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="d19c8-118">Elle n'inclut pas les spécificateurs facultatifs pour le propriétaire, le nom de la base de données et le numéro de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="d19c8-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="d19c8-119">Étant donné qu'il est valide d'appeler **srv_rpcname** lorsqu'il n'y a pas de procédure stockée distante (aucune erreur informative ne se produit), cette fonction fournit une méthode pour déterminer si une procédure stockée distante existe.</span><span class="sxs-lookup"><span data-stu-id="d19c8-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d19c8-120">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="d19c8-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d19c8-121">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d19c8-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
