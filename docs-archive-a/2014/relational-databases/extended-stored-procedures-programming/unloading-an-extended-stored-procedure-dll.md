---
title: Déchargement d’une DLL de procédure stockée étendue | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], unloading
- unloading extended stored procedures
ms.assetid: 4c75ab14-af54-4965-b376-8d75d385c941
author: rothja
ms.author: jroth
ms.openlocfilehash: 7bd4855390e95d949ab769d6567d6f106959dcde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600016"
---
# <a name="unloading-an-extended-stored-procedure-dll"></a><span data-ttu-id="08010-102">Déchargement d'une DLL de procédure stockée étendue</span><span class="sxs-lookup"><span data-stu-id="08010-102">Unloading an Extended Stored Procedure DLL</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="08010-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="08010-103">Use CLR Integration instead.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="08010-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]charge une dll de procédure stockée étendue dès qu’un appel est effectué à l’une des fonctions de la dll.</span><span class="sxs-lookup"><span data-stu-id="08010-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] loads an extended stored procedure DLL as soon as a call is made to one of the functions of the DLL.</span></span> <span data-ttu-id="08010-105">La DLL reste chargée jusqu'à ce que le serveur soit arrêté ou jusqu'à ce que l'administrateur système utilise l'instruction DBCC pour la décharger.</span><span class="sxs-lookup"><span data-stu-id="08010-105">The DLL remains loaded until the server is shut down or until the system administrator uses the DBCC statement to unload it.</span></span> <span data-ttu-id="08010-106">Par exemple, cette commande décharge le **xp_hello.dll**, ce qui permet à l’administrateur système de copier une version plus récente de ce fichier dans le répertoire sans arrêter le serveur :</span><span class="sxs-lookup"><span data-stu-id="08010-106">For example, this command unloads the **xp_hello.dll**, allowing the system administrator to copy a newer version of this file to the directory without shutting down the server:</span></span>  
  
```  
DBCC xp_hello(FREE)  
```  
  
## <a name="see-also"></a><span data-ttu-id="08010-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08010-107">See Also</span></span>  
 [<span data-ttu-id="08010-108">DBCC DllName &#40;FREE&#41; &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="08010-108">DBCC dllname &#40;FREE&#41; &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dllname-free-transact-sql)  
  
  
