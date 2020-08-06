---
title: srv_rpcdb (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707568"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="7eebc-102">srv_rpcdb (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="7eebc-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7eebc-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="7eebc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="7eebc-104">Retourne le composant de nom de base de données pour la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="7eebc-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eebc-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7eebc-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="7eebc-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="7eebc-106">Arguments</span></span>  
 <span data-ttu-id="7eebc-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="7eebc-107">*srvproc*</span></span>  
 <span data-ttu-id="7eebc-108">Pointeur vers la structure SRV_PROC qui est le handle pour une connexion cliente particulière.</span><span class="sxs-lookup"><span data-stu-id="7eebc-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="7eebc-109">La structure contient des informations que la bibliothèque d'API de procédure stockée étendue utilise pour gérer les communications et les données entre l'application et le client.</span><span class="sxs-lookup"><span data-stu-id="7eebc-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="7eebc-110">*Len*</span><span class="sxs-lookup"><span data-stu-id="7eebc-110">*len*</span></span>  
 <span data-ttu-id="7eebc-111">Pointeur vers une variable `int` qui reçoit la longueur du nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="7eebc-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="7eebc-112">Si *len* a la valeur NULL, la longueur du nom de la base de données n’est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="7eebc-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="7eebc-113">Retours</span><span class="sxs-lookup"><span data-stu-id="7eebc-113">Returns</span></span>  
 <span data-ttu-id="7eebc-114">Pointeur DBCHAR vers la chaîne terminée par le caractère NULL pour la partie du nom de base de données de la procédure stockée distante actuelle.</span><span class="sxs-lookup"><span data-stu-id="7eebc-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="7eebc-115">S’il n’y a pas de procédure stockée distante actuelle, NULL est retourné et le paramètre *len* prend la valeur -1.</span><span class="sxs-lookup"><span data-stu-id="7eebc-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eebc-116">Notes</span><span class="sxs-lookup"><span data-stu-id="7eebc-116">Remarks</span></span>  
 <span data-ttu-id="7eebc-117">Cette fonction retourne uniquement le composant de base de données du nom d'objet de la procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="7eebc-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="7eebc-118">Elle n'inclut pas les spécificateurs facultatifs pour le propriétaire, le nom de procédure stockée distante et le numéro de procédure stockée distante.</span><span class="sxs-lookup"><span data-stu-id="7eebc-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7eebc-119">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="7eebc-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="7eebc-120">Pour plus d'informations sur l'examen et les tests de sécurité, consultez ce [site Web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="7eebc-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
