---
title: Guide pratique pour gérer une instance CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695967"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="645d0-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="645d0-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="645d0-103">Cette procédure décrit comment utiliser la console du concepteur CDC pour gérer les opérations d'instance de capture de données modifiées au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="645d0-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="645d0-104">Pour gérer les opérations d'instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="645d0-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="645d0-105">Dans le menu **Démarrer** , sélectionnez **Console du concepteur de capture de données modifiées**.</span><span class="sxs-lookup"><span data-stu-id="645d0-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="645d0-106">Dans le volet gauche, développez **Capture de données modifiées** , puis le service qui contient l'instance que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="645d0-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="645d0-107">Sélectionnez le nom de l'instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="645d0-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="645d0-108">Dans le volet **Actions** à droite de la console du concepteur CDC, cliquez sur l'opération à effectuer.</span><span class="sxs-lookup"><span data-stu-id="645d0-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="645d0-109">Vous pouvez également cliquer avec le bouton droit sur le nom de l'instance dans le volet gauche et sélectionner l'opération à effectuer.</span><span class="sxs-lookup"><span data-stu-id="645d0-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="645d0-110">Vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="645d0-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="645d0-111">**Démarrer** : pour lancer la capture des modifications.</span><span class="sxs-lookup"><span data-stu-id="645d0-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="645d0-112">**Arrêter** : pour arrêter la capture des modifications.</span><span class="sxs-lookup"><span data-stu-id="645d0-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="645d0-113">**Réinitialiser** : Cliquez sur **Réinitialiser** pour rétablir l’état (vide) initial de l’instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="645d0-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="645d0-114">Cette option est disponible lorsque l'instance de capture de données modifiées est arrêtée.</span><span class="sxs-lookup"><span data-stu-id="645d0-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="645d0-115">Toutes les modifications des tables de modifications et de l'état interne de l'instance de capture de données modifiées sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="645d0-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="645d0-116">Lorsque l'instance de capture de données modifiées est démarrée ultérieurement, la capture de modifications démarre à partir de ce point et inclut uniquement les transactions qui ont démarré après que l'instance de capture de données modifiées a démarré.</span><span class="sxs-lookup"><span data-stu-id="645d0-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="645d0-117">**Supprimer** : pour supprimer l’instance CDC.</span><span class="sxs-lookup"><span data-stu-id="645d0-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="645d0-118">**Script de journalisation Oracle** : cliquez sur ce lien pour afficher la boîte de dialogue du script de journalisation Oracle contenant le script de journalisation supplémentaire Oracle.</span><span class="sxs-lookup"><span data-stu-id="645d0-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="645d0-119">Pour plus d'informations sur les opérations réalisables dans cette boîte de dialogue, consultez [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="645d0-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="645d0-120">**Remarque** : Lorsque vous exécutez des scripts de journalisation supplémentaires, la boîte de dialogue des informations d'identification Oracle pour l'exécution de script s'ouvre et vous permet de spécifier un nom d'utilisateur et un mot de passe Oracle valides.</span><span class="sxs-lookup"><span data-stu-id="645d0-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="645d0-121">Pour plus d'informations sur la façon de fournir les informations d'identification Oracle appropriées, consultez [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="645d0-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="645d0-122">**Déploiement d’instance CDC** : pour générer un script de déploiement de l’instance CDC.</span><span class="sxs-lookup"><span data-stu-id="645d0-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="645d0-123">Pour plus d'informations sur cette boîte de dialogue, consultez [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="645d0-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="645d0-124">Pour plus d'informations sur ces tâches, consultez [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="645d0-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="645d0-125">Vous pouvez également sélectionner **Propriétés** pour modifier les propriétés de configuration de l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="645d0-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="645d0-126">Pour plus d'informations sur la modification des propriétés d'une instance de capture de données modifiées, consultez [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="645d0-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
