---
title: Propriétés de l’alerte-nouvelle alerte (page réponse) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705903"
---
# <a name="alert-properties-new-alert-response-page"></a><span data-ttu-id="cc7b0-102">Propriétés de l’alerte-nouvelle alerte (page réponse)</span><span class="sxs-lookup"><span data-stu-id="cc7b0-102">Alert Properties-New Alert (Response Page)</span></span>
  <span data-ttu-id="cc7b0-103">Utilisez cette page pour spécifier un travail que vous souhaitez exécuter et pour obtenir une liste d’opérateurs à notifier en réponse à une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerte de l’agent.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-103">Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cc7b0-104">Options</span><span class="sxs-lookup"><span data-stu-id="cc7b0-104">Options</span></span>  
 <span data-ttu-id="cc7b0-105">**Exécuter le travail**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-105">**Execute job**</span></span>  
 <span data-ttu-id="cc7b0-106">Active les options **Liste des travaux**, **Nouveau travail** et **Afficher le travail** .</span><span class="sxs-lookup"><span data-stu-id="cc7b0-106">Enables the **Job list**, **New job** and **View job** options.</span></span>  
  
 <span data-ttu-id="cc7b0-107">**Nouveau travail**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-107">**New job**</span></span>  
 <span data-ttu-id="cc7b0-108">Ouvre la boîte de dialogue **Nouveau travail** .</span><span class="sxs-lookup"><span data-stu-id="cc7b0-108">Open the **New Job** dialog box.</span></span> <span data-ttu-id="cc7b0-109">Ce bouton n'est pas disponible lorsque **Exécuter le travail** n'est pas sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-109">This button is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="cc7b0-110">**Afficher le travail**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-110">**View job**</span></span>  
 <span data-ttu-id="cc7b0-111">Permet d'afficher et de modifier le travail sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-111">View or modify the selected job.</span></span> <span data-ttu-id="cc7b0-112">Cette option n'est pas disponible lorsque **Exécuter le travail** n'est pas sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-112">This option is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="cc7b0-113">**Notifier les opérateurs**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-113">**Notify operators**</span></span>  
 <span data-ttu-id="cc7b0-114">Active les contrôles qui vous permettent d'ajouter, de supprimer ou de modifier des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-114">Enables the controls that allow you to add, remove, or change operators.</span></span>  
  
 <span data-ttu-id="cc7b0-115">**Liste d'opérateurs**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-115">**Operator list**</span></span>  
 <span data-ttu-id="cc7b0-116">Répertorie les opérateurs à notifier lorsqu'une alerte se produit.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-116">Lists the operators to notify when an alert occurs.</span></span> <span data-ttu-id="cc7b0-117">Pour spécifier une méthode de notification, cochez la case **Messagerie électronique**, **Radiomessagerie**ou **Envoi réseau** affichée après le nom de l’opérateur. Cette option n’est pas disponible quand **Notifier les opérateurs** n’est pas sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-117">To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.</span></span>  
  
 <span data-ttu-id="cc7b0-118">**Courriel**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-118">**E-mail**</span></span>  
 <span data-ttu-id="cc7b0-119">Utilisez un courrier électronique pour notifier l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-119">Use e-mail to notify the operator.</span></span>  
  
 <span data-ttu-id="cc7b0-120">**Radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-120">**Pager**</span></span>  
 <span data-ttu-id="cc7b0-121">Utilisez une adresse de radiomessagerie pour notifier l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-121">Use the pager e-mail address to notify the operator.</span></span>  
  
 <span data-ttu-id="cc7b0-122">**Envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-122">**Net send**</span></span>  
 <span data-ttu-id="cc7b0-123">Utilisez **net send** pour notifier l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-123">Use **net send** to notify the operator.</span></span>  
  
 <span data-ttu-id="cc7b0-124">**Nouvel opérateur**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-124">**New operator**</span></span>  
 <span data-ttu-id="cc7b0-125">Affiche la boîte de dialogue **Nouvel opérateur** , que vous pouvez utiliser pour créer un opérateur.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-125">Displays the **New Operator** dialog box, which you can use to create a new operator.</span></span>  
  
 <span data-ttu-id="cc7b0-126">**Afficher l'opérateur**</span><span class="sxs-lookup"><span data-stu-id="cc7b0-126">**View operator**</span></span>  
 <span data-ttu-id="cc7b0-127">Affiche la boîte de dialogue **Propriétés** pour l’opérateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-127">Displays the **Properties** dialog box for the currently selected operator.</span></span> <span data-ttu-id="cc7b0-128">Vous pouvez afficher et modifier les propriétés d’opérateur dans la boîte de dialogue **Propriétés Opérateur**.</span><span class="sxs-lookup"><span data-stu-id="cc7b0-128">You can view and modified operator properties on the **Operator Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc7b0-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cc7b0-129">See Also</span></span>  
 <span data-ttu-id="cc7b0-130">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b0-130">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="cc7b0-131">[Créer une alerte à l’aide d’un niveau de gravité](create-an-alert-using-severity-level.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b0-131">[Create an Alert Using Severity Level](create-an-alert-using-severity-level.md) </span></span>  
 <span data-ttu-id="cc7b0-132">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b0-132">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="cc7b0-133">[Modifier une alerte](edit-an-alert.md) </span><span class="sxs-lookup"><span data-stu-id="cc7b0-133">[Edit an Alert](edit-an-alert.md) </span></span>  
 [<span data-ttu-id="cc7b0-134">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="cc7b0-134">Delete an Alert</span></span>](delete-an-alert.md)  
  
  
