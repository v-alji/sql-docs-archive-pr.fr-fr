---
title: Inverser une transaction (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698345"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="1ac3c-102">Inverser une transaction (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1ac3c-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="1ac3c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], les administrateurs peuvent inverser une transaction lorsqu'une action doit être annulée.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="1ac3c-104">Les exemples de transactions sont les suivants : modifications apportées aux valeurs d'attribut, déplacements de hiérarchie ou suppressions de membres.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1ac3c-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="1ac3c-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="1ac3c-106">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="1ac3c-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="1ac3c-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-107">You must be a model administrator.</span></span> <span data-ttu-id="1ac3c-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ac3c-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="1ac3c-109">Pour inverser une transaction</span><span class="sxs-lookup"><span data-stu-id="1ac3c-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="1ac3c-110">Dans la page d’accueil de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="1ac3c-111">Dans la barre de menus, cliquez sur **Transactions**.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="1ac3c-112">Dans la page **Transactions** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="1ac3c-113">Dans la liste **Version** , sélectionnez une version.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="1ac3c-114">Cliquez dans la grille sur la ligne correspondant à la transaction que vous souhaitez inverser.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="1ac3c-115">Cliquez sur **Inverser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="1ac3c-116">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="1ac3c-117">Une autre transaction est ajoutée à la grille pour enregistrer la transaction inversée.</span><span class="sxs-lookup"><span data-stu-id="1ac3c-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ac3c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ac3c-118">See Also</span></span>  
 <span data-ttu-id="1ac3c-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1ac3c-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="1ac3c-120">Réactiver un membre ou une collection &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ac3c-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  
