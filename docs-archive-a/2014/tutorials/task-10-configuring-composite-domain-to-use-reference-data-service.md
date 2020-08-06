---
title: 'Tâche 10 : configuration d’un domaine composite pour utiliser le service de données de référence | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710067"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="1d62c-102">Tâche 10 : Configuration d’un domaine pour utiliser un service de données de référence</span><span class="sxs-lookup"><span data-stu-id="1d62c-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="1d62c-103">Dans cette tâche, vous configurez le domaine composite **validation d’adresse** pour utiliser le service de **vérification d’adresse de données Melissa** .</span><span class="sxs-lookup"><span data-stu-id="1d62c-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="1d62c-104">Au moment de l'exécution, pendant l'activité de nettoyage, DQS passe les valeurs des domaines du domaine Validation d'adresses au service pour le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="1d62c-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="1d62c-105">Pour plus d’informations, consultez mapper un domaine [/domaine composite à des données de référence](https://msdn.microsoft.com/library/hh213030.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1d62c-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="1d62c-106">Dans la page principale du **client DQS**, cliquez sur **Suppliers (Domain Management)** sous **bases de connaissances récentes** pour lancer la page de **gestion des domaines** .</span><span class="sxs-lookup"><span data-stu-id="1d62c-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="1d62c-107">Sélectionnez le domaine composite **validation d’adresse** dans la **liste des domaines**.</span><span class="sxs-lookup"><span data-stu-id="1d62c-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="1d62c-108">Dans le volet droit, basculez vers l’onglet **données de référence** .</span><span class="sxs-lookup"><span data-stu-id="1d62c-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="1d62c-109">![Onglet Données de référence](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Onglet Données de référence")</span><span class="sxs-lookup"><span data-stu-id="1d62c-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="1d62c-110">Cliquez sur le bouton **Parcourir** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="1d62c-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="1d62c-111">Dans la boîte de dialogue **catalogue des fournisseurs de données de référence en ligne** , **cochez la case en regard de** **Melissa Data-adresse Check**.</span><span class="sxs-lookup"><span data-stu-id="1d62c-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="1d62c-112">![Sélectionner Melissa Data – Contrôle d'adresse](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Sélectionner Melissa Data – Contrôle d'adresse")</span><span class="sxs-lookup"><span data-stu-id="1d62c-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="1d62c-113">Dans le volet droit, dans la section **schéma** , mappez **Address ligne** Domain à l’élément de schéma **address line (M)** à l’aide de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="1d62c-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="1d62c-114">![Mapper l'élément de schéma RDS au domaine](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Mapper l'élément de schéma RDS au domaine")</span><span class="sxs-lookup"><span data-stu-id="1d62c-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="1d62c-115">Cliquez sur le bouton **Ajouter une entrée de schéma (+)** dans la barre d’outils pour créer une entrée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1d62c-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="1d62c-116">![Bouton à la barre d'outils Ajouter une entrée de schéma](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Bouton à la barre d'outils Ajouter une entrée de schéma")</span><span class="sxs-lookup"><span data-stu-id="1d62c-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="1d62c-117">Mappez les domaines DQS suivants à l'aide des listes déroulantes, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="1d62c-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="1d62c-118">![Mapper les éléments de schéma RDS aux domaines](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Mapper les éléments de schéma RDS aux domaines")</span><span class="sxs-lookup"><span data-stu-id="1d62c-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="1d62c-119">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="1d62c-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1d62c-120">étape suivante</span><span class="sxs-lookup"><span data-stu-id="1d62c-120">Next Step</span></span>  
 [<span data-ttu-id="1d62c-121">Tâche 11 : Publication de la base de connaissances</span><span class="sxs-lookup"><span data-stu-id="1d62c-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
