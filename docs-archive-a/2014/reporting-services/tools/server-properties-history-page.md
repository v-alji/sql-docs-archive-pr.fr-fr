---
title: Propriétés du serveur (page Historique) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610965"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="33d08-102">Propriétés du serveur (page Historique)</span><span class="sxs-lookup"><span data-stu-id="33d08-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="33d08-103">Utilisez cette page pour définir le nombre de copies par défaut que l'historique de rapport peut conserver.</span><span class="sxs-lookup"><span data-stu-id="33d08-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="33d08-104">La valeur par défaut fournit un paramètre initial qui établit les limites de l'historique de tous les rapports.</span><span class="sxs-lookup"><span data-stu-id="33d08-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="33d08-105">Ces paramètres sont modifiables pour chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="33d08-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="33d08-106">L'historique de rapport est une collection d'instantanés de rapport qui incluent des données de rapport et une mise en page qui s'appliquent au rapport au moment où l'instantané est créé.</span><span class="sxs-lookup"><span data-stu-id="33d08-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="33d08-107">Vous pouvez utiliser l'historique de rapport pour garder une copie d'un rapport tel qu'il se présentait à une date ou heure spécifique.</span><span class="sxs-lookup"><span data-stu-id="33d08-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="33d08-108">Vous pouvez créer et gérer l'historique de rapport pour des rapports individuels qui s'exécutent sur un serveur de rapports en mode natif ou configuré pour le mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="33d08-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="33d08-109">Les instantanés d'historique de rapport sont stockés dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="33d08-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="33d08-110">Si vous conservez un nombre illimité d'instantanés, veillez à vérifier régulièrement la taille de la base de données pour vous assurer qu'elle n'augmente pas trop rapidement ni n'utilise trop d'espace disque.</span><span class="sxs-lookup"><span data-stu-id="33d08-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="33d08-111">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à une instance de serveur de rapports, cliquez avec le bouton droit sur le nom du serveur de rapports, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="33d08-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="33d08-112">Cliquez sur **Historique** pour ouvrir cette page.</span><span class="sxs-lookup"><span data-stu-id="33d08-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="33d08-113">Options</span><span class="sxs-lookup"><span data-stu-id="33d08-113">Options</span></span>  
 <span data-ttu-id="33d08-114">**Conserver un nombre illimité d'instantanés dans l'historique de rapport**</span><span class="sxs-lookup"><span data-stu-id="33d08-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="33d08-115">Conservez tous les instantanés d'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="33d08-115">Retain all report history snapshots.</span></span> <span data-ttu-id="33d08-116">Vous devez supprimer manuellement des instantanés pour réduire la taille de l'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="33d08-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="33d08-117">**Limiter les copies de l'historique de rapport**</span><span class="sxs-lookup"><span data-stu-id="33d08-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="33d08-118">Conservez un nombre défini d'instantanés d'historique de rapport.</span><span class="sxs-lookup"><span data-stu-id="33d08-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="33d08-119">Lorsque la limite est atteinte, des copies anciennes sont supprimées de l'historique de rapport pour libérer de l'espace pour les nouvelles copies.</span><span class="sxs-lookup"><span data-stu-id="33d08-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="33d08-120">Si vous limitez l'historique de rapport ultérieurement, le serveur de rapports applique la nouvelle limite à l'historique de rapport existant dès que celui-ci la dépasse.</span><span class="sxs-lookup"><span data-stu-id="33d08-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="33d08-121">Les instantanés de rapport les plus anciens sont supprimés en premier.</span><span class="sxs-lookup"><span data-stu-id="33d08-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="33d08-122">Si l'historique de rapport est vide ou n'a pas atteint la limite, de nouveaux instantanés de rapport sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="33d08-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="33d08-123">Lorsque la limite est atteinte, l'instantané le plus ancien est supprimé dès qu'un nouvel instantané est ajouté.</span><span class="sxs-lookup"><span data-stu-id="33d08-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d08-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33d08-124">See Also</span></span>  
 <span data-ttu-id="33d08-125">[Définir les propriétés du serveur de rapports &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="33d08-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="33d08-126">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="33d08-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="33d08-127">Aide du serveur de rapports dans Management Studio accessible par la touche F1</span><span class="sxs-lookup"><span data-stu-id="33d08-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
