---
title: Activer l’option Verrouiller les pages en mémoire (Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Lock Pages in Memory option
ms.assetid: cd581fbc-4747-439e-87f9-2f18e39c5bb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13290940c3a94a7ba79582d892a5e28670f24b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605723"
---
# <a name="enable-the-lock-pages-in-memory-option-windows"></a><span data-ttu-id="6d1a9-102">Activer l'option Verrouiller les pages en mémoire (Windows)</span><span class="sxs-lookup"><span data-stu-id="6d1a9-102">Enable the Lock Pages in Memory Option (Windows)</span></span>
  <span data-ttu-id="6d1a9-103">Cette stratégie Windows détermine quels comptes peuvent utiliser un processus destiné à conserver les données en mémoire physique pour éviter leur pagination en mémoire virtuelle sur le disque.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-103">This Windows policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d1a9-104">Le verrouillage des pages en mémoire permet d'optimiser les performances lorsque la pagination de la mémoire sur disque est prévue.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-104">Locking pages in memory may boost performance when paging memory to disk is expected.</span></span>  
  
 <span data-ttu-id="6d1a9-105">L'outil Stratégie de groupe de Windows (gpedit.msc) vous permet d'activer cette stratégie pour le compte utilisé par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d1a9-105">Use the Windows Group Policy tool (gpedit.msc) to enable this policy for the account used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6d1a9-106">Vous devez être administrateur système pour modifier cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-106">You must be a system administrator to change this policy.</span></span>  
  
### <a name="to-enable-the-lock-pages-in-memory-option"></a><span data-ttu-id="6d1a9-107">Pour activer l'option Verrouiller les pages en mémoire</span><span class="sxs-lookup"><span data-stu-id="6d1a9-107">To enable the lock pages in memory option</span></span>  
  
1.  <span data-ttu-id="6d1a9-108">Dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-108">On the **Start** menu, click **Run**.</span></span> <span data-ttu-id="6d1a9-109">Dans la zone **ouvrir** , tapez `gpedit.msc` .</span><span class="sxs-lookup"><span data-stu-id="6d1a9-109">In the **Open** box, type `gpedit.msc`.</span></span>  
  
2.  <span data-ttu-id="6d1a9-110">Sur la console **Éditeur de stratégie de groupe locale** , développez **Configuration ordinateur**, puis **Paramètres Windows**.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-110">On the **Local Group Policy Editor** console, expand **Computer Configuration**, and then expand **Windows Settings**.</span></span>  
  
3.  <span data-ttu-id="6d1a9-111">Développez **Paramètres de sécurité**, puis **Stratégies locales**.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-111">Expand **Security Settings**, and then expand **Local Policies**.</span></span>  
  
4.  <span data-ttu-id="6d1a9-112">Sélectionnez le dossier **Attribution des droits utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="6d1a9-112">Select the **User Rights Assignment** folder.</span></span>  
  
     <span data-ttu-id="6d1a9-113">Les stratégies s'affichent dans le volet Détails.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-113">The policies will be displayed in the details pane.</span></span>  
  
5.  <span data-ttu-id="6d1a9-114">Dans le volet, double-cliquez sur **Verrouiller les pages en mémoire**.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-114">In the pane, double-click **Lock pages in memory**.</span></span>  
  
6.  <span data-ttu-id="6d1a9-115">Dans la boîte de dialogue **Paramètre de sécurité locale - Verrouiller les pages en mémoire**, cliquez sur **Ajouter un utilisateur ou un groupe**.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-115">In the **Local Security Setting - Lock pages in memory** dialog box, click **Add User or Group**.</span></span>  
  
7.  <span data-ttu-id="6d1a9-116">Dans la boîte de dialogue **Sélectionner des utilisateurs, des comptes de service ou des groupes** , ajoutez un compte avec les privilèges nécessaires pour exécuter sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-116">In the **Select Users, Service Accounts, or Groups** dialog box, add an account with privileges to run sqlservr.exe.</span></span>  
  
8.  <span data-ttu-id="6d1a9-117">Fermez la session, puis rouvrez-la pour que cette modification prenne effet.</span><span class="sxs-lookup"><span data-stu-id="6d1a9-117">Log out and then log back in for this change to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1a9-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d1a9-118">See Also</span></span>  
 [<span data-ttu-id="6d1a9-119">server memory (options de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="6d1a9-119">Server Memory Server Configuration Options</span></span>](server-memory-server-configuration-options.md)  
  
  
