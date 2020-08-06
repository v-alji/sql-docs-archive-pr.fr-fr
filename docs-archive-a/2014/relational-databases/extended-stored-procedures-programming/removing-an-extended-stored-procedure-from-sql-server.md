---
title: Suppression d’une procédure stockée étendue de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 284da815de073248669da032c06ddeeb68c697a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710616"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a><span data-ttu-id="ccc5b-102">Suppression d'une procédure stockée étendue de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ccc5b-102">Removing an Extended Stored Procedure from SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ccc5b-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="ccc5b-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="ccc5b-104">Pour supprimer chaque fonction de procédure stockée étendue dans une DLL de procédure stockée étendue définie par l’utilisateur, un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrateur système doit exécuter la procédure stockée système **sp_dropextendedproc** , en spécifiant le nom de la fonction et le nom de la dll dans laquelle cette fonction réside.</span><span class="sxs-lookup"><span data-stu-id="ccc5b-104">To drop each extended stored procedure function in a user-defined extended stored procedure DLL, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must run the **sp_dropextendedproc** system stored procedure, specifying the name of the function and the name of the DLL in which that function resides.</span></span> <span data-ttu-id="ccc5b-105">Par exemple, cette commande supprime la fonction **xp_hello**, située dans une DLL nommée xp_hello.dll, à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ccc5b-105">For example, this command removes the function **xp_hello**, located in a DLL named xp_hello.dll, from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="ccc5b-106">À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** ne supprime pas les procédures stockées étendues du système.</span><span class="sxs-lookup"><span data-stu-id="ccc5b-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], **sp_dropextendedproc** does not drop system extended stored procedures.</span></span> <span data-ttu-id="ccc5b-107">Au lieu de cela, l’administrateur système doit refuser l’autorisation EXECUTe sur la procédure stockée étendue au rôle **public** .</span><span class="sxs-lookup"><span data-stu-id="ccc5b-107">Instead, the system administrator should deny EXECUTE permission on the extended stored procedure to the **public** role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc5b-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ccc5b-108">See Also</span></span>  
 [<span data-ttu-id="ccc5b-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ccc5b-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
