---
title: Valeurs HOST_NAME | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.hostnamevalue.f1
ms.assetid: 21548f08-2910-4a55-baac-b911ba9afaf1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 67d01df05c8d56fd435eb0ee1b42ba2da6a312ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601334"
---
# <a name="host_name-values"></a><span data-ttu-id="ace32-102">Valeurs HOST_NAME</span><span class="sxs-lookup"><span data-stu-id="ace32-102">HOST_NAME Values</span></span>
  <span data-ttu-id="ace32-103">Les publications de fusion associées à des filtres paramétrés utilisent la fonction SUSER_SNAME() et/ou HOST_NAME() pour filtrer les données.</span><span class="sxs-lookup"><span data-stu-id="ace32-103">Merge publications with parameterized filters use the SUSER_SNAME() function and/or the HOST_NAME() function to filter data.</span></span> <span data-ttu-id="ace32-104">La fonction concernée est spécifiée dans l'Assistant Nouvelle publication ou la boîte de dialogue **Propriétés de la publication** .</span><span class="sxs-lookup"><span data-stu-id="ace32-104">The function is specified in the New Publication Wizard or the **Publication Properties** dialog box.</span></span>  
  
 <span data-ttu-id="ace32-105">Par défaut, la fonction HOST_NAME() retourne le nom de l'ordinateur qui se connecte au serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="ace32-105">By default, the HOST_NAME() function returns the name of the computer connecting to the Publisher.</span></span> <span data-ttu-id="ace32-106">Lors de l'utilisation de filtres paramétrés, il est fréquent de remplacer cette valeur par une autre dans cette page de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="ace32-106">When using parameterized filters, it is common to override this value by supplying a value on this page of the wizard.</span></span> <span data-ttu-id="ace32-107">La fonction HOST_NAME() retourne alors la valeur spécifiée à la place du nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ace32-107">The HOST_NAME() function then returns the value you specify rather than the name of the computer.</span></span> <span data-ttu-id="ace32-108">Pour plus d’informations, consultez la section « Substitution de la valeur de HOST_NAME() » dans [Filtres paramétrés - Filtres de lignes paramétrés](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="ace32-108">For more information, see the "Overriding the HOST_NAME() Value" section of [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ace32-109">Si vous remplacez la valeur de HOST_NAME(), tous les appels de la fonction HOST_NAME() retourneront la valeur que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ace32-109">If you override HOST_NAME(), all calls to the HOST_NAME() function will return the value you specify.</span></span> <span data-ttu-id="ace32-110">Assurez-vous que les autres applications ne dépendent pas de la fonction HOST_NAME() avec retour du nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ace32-110">Ensure that other applications are not depending on HOST_NAME() returning the computer name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ace32-111">Options</span><span class="sxs-lookup"><span data-stu-id="ace32-111">Options</span></span>  
 <span data-ttu-id="ace32-112">**Propriétés de l'abonnement**</span><span class="sxs-lookup"><span data-stu-id="ace32-112">**Subscription properties**</span></span>  
 <span data-ttu-id="ace32-113">Entrez une valeur pour chaque abonné dans la colonne **Valeur HOST_NAME** ou acceptez la valeur par défaut, c'est-à-dire le nom de l'ordinateur de l'abonné.</span><span class="sxs-lookup"><span data-stu-id="ace32-113">Enter a value for each Subscriber in the **HOST_NAME Value** column or accept the default, which is the name of the Subscriber computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace32-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ace32-114">See Also</span></span>  
 <span data-ttu-id="ace32-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="ace32-115">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="ace32-116">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="ace32-116">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 <span data-ttu-id="ace32-117">[Afficher et modifier les propriétés d’un abonnement par extraction](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ace32-117">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="ace32-118">[Afficher et modifier les propriétés d’un abonnement par émission de données](view-and-modify-push-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ace32-118">[View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) </span></span>  
 <span data-ttu-id="ace32-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ace32-119">[HOST_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/host-name-transact-sql) </span></span>  
 [<span data-ttu-id="ace32-120">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="ace32-120">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
