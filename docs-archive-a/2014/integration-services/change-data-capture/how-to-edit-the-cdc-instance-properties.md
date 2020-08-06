---
title: Guide pratique pour modifier les propriétés d’une instance CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695968"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="6e142-102">Procédure : modifier les propriétés d'une instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="6e142-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="6e142-103">Cette procédure décrit comment utiliser la console du concepteur CDC pour modifier les propriétés de configuration d'une instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="6e142-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="6e142-104">Pour modifier les propriétés de configuration de l'instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="6e142-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="6e142-105">Dans le menu **Démarrer** , sélectionnez **Console du concepteur de capture de données modifiées**.</span><span class="sxs-lookup"><span data-stu-id="6e142-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="6e142-106">Dans le volet gauche, développez **Capture de données modifiées** , puis le service qui contient l'instance avec les propriétés à modifier.</span><span class="sxs-lookup"><span data-stu-id="6e142-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="6e142-107">Sélectionnez le nom de l'instance où vous souhaitez modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="6e142-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="6e142-108">Dans le volet Actions à droite de la console du concepteur CDC, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6e142-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="6e142-109">Vous pouvez aussi cliquer avec le bouton droit sur l’instance dont vous voulez modifier les propriétés et cliquer sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6e142-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="6e142-110">Dans l'éditeur de propriétés, modifiez les propriétés dans les onglets suivants :</span><span class="sxs-lookup"><span data-stu-id="6e142-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="6e142-111">**Oracle**: l'onglet **Oracle** de l'éditeur de propriétés permet d'apporter des modifications à la description que vous avez fournie dans la page Créer une base de données CDC de l'Assistant Nouvelle instance et d'apporter des modifications aux informations de connexion à la base de données d'exploration de données de journaux Oracle.</span><span class="sxs-lookup"><span data-stu-id="6e142-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="6e142-112">Pour plus d'informations sur ce que vous pouvez modifier dans cet onglet, consultez [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6e142-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="6e142-113">**Tables**: l'onglet **Tables** permet d'apporter des modifications aux tables et aux colonnes sélectionnées dans la base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="6e142-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="6e142-114">Pour plus d'informations sur ce que vous pouvez modifier dans cet onglet, consultez [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6e142-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="6e142-115">**Scripts**: l’onglet **Scripts** permet d’exécuter ou de réexécuter un script sur la base de données source Oracle qui configure une journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="6e142-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="6e142-116">Pour plus d'informations sur ce que vous pouvez faire dans cet onglet, consultez [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="6e142-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="6e142-117">**Avancé**: l'onglet **Avancé** permet d'ajouter des propriétés spéciales à l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="6e142-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="6e142-118">Pour plus d'informations sur ce que vous pouvez faire dans cet onglet, consultez [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6e142-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
