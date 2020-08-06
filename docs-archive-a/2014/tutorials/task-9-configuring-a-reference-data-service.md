---
title: 'Tâche 9 : configuration d’un service de données de référence | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d0535fce-2bf5-4f6d-b517-ffe6fa13738d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1e7c685de13a2f5c495482f816818ff6b838fc7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710004"
---
# <a name="task-9-configuring-a-reference-data-service"></a><span data-ttu-id="17487-102">Tâche 9 : Configuration d’un service de données de référence</span><span class="sxs-lookup"><span data-stu-id="17487-102">Task 9: Configuring a Reference Data Service</span></span>
  <span data-ttu-id="17487-103">Dans cette tâche, vous allez configurer DQS pour utiliser un service de données de référence sur la place de marché Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="17487-103">In this task, you configure DQS to use a Reference Data Service on Azure Marketplace.</span></span> <span data-ttu-id="17487-104">Dans la tâche suivante, vous allez configurer le domaine **Validation d'adresses** pour utiliser ce service.</span><span class="sxs-lookup"><span data-stu-id="17487-104">In the next task, you will configure the **Address Validation** domain to use this service.</span></span> <span data-ttu-id="17487-105">Au moment de l’exécution, pendant l’activité de nettoyage, DQS passe les valeurs des domaines dans le domaine de **validation d’adresse** au service pour le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="17487-105">At runtime, during cleansing activity, DQS passes the values of domains in the **Address Validation** domain to the service for cleansing.</span></span> <span data-ttu-id="17487-106">Consultez [Configurer DQS pour utiliser des données de référence](https://msdn.microsoft.com/library/hh213070.aspx) pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="17487-106">See [Configure DQS to Use Reference Data](https://msdn.microsoft.com/library/hh213070.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="17487-107">Dans la page principale du **Client DQS**, cliquez sur **Configuration** dans le volet **Administration**.</span><span class="sxs-lookup"><span data-stu-id="17487-107">In the main page of **DQS Client**, in the **Administration** pane, click **Configuration**.</span></span>  
  
2.  <span data-ttu-id="17487-108">Assurez-vous que l'onglet **Données de référence** est actif.</span><span class="sxs-lookup"><span data-stu-id="17487-108">Ensure that **Reference Data** tab is active.</span></span>  
  
3.  <span data-ttu-id="17487-109">Dans la zone **Paramètres réseau** , entrez les valeurs appropriées dans les champs **Serveur proxy** et **Port** si vous devez utiliser un serveur proxy pour vous connecter à Internet.</span><span class="sxs-lookup"><span data-stu-id="17487-109">In the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** fields if you need to use a proxy server to connect to Internet.</span></span>  
  
4.  <span data-ttu-id="17487-110">Tapez votre **clé de compte Azure Marketplace** pour le champ **ID de compte DataMarket** .</span><span class="sxs-lookup"><span data-stu-id="17487-110">Type your **Azure Marketplace Account Key** for the **DataMarket Account ID** field.</span></span>  
  
     <span data-ttu-id="17487-111">![Compte de service de données de référence d'Azure Data Market](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Compte de service de données de référence d'Azure Data Market")</span><span class="sxs-lookup"><span data-stu-id="17487-111">![Azure Data Market Reference Data Service Account](../../2014/tutorials/media/et-configuringareferencedataservice.jpg "Azure Data Market Reference Data Service Account")</span></span>  
  
5.  <span data-ttu-id="17487-112">Cliquez sur le bouton **Valider** en regard de la zone de texte pour valider l'ID de compte.</span><span class="sxs-lookup"><span data-stu-id="17487-112">Click **Validate** button next to the text box to validate the account ID.</span></span>  
  
6.  <span data-ttu-id="17487-113">Cliquez sur **OK** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="17487-113">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="17487-114">Cliquez sur **Fermer** en bas de la page pour passer à la page principale du Client DQS.</span><span class="sxs-lookup"><span data-stu-id="17487-114">Click **Close** at the bottom of the page to switch to the main page of DQS Client.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="17487-115">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="17487-115">Next Task</span></span>  
 [<span data-ttu-id="17487-116">Tâche 10 : Configuration d’un domaine pour utiliser un service de données de référence</span><span class="sxs-lookup"><span data-stu-id="17487-116">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>](../../2014/tutorials/task-10-configuring-composite-domain-to-use-reference-data-service.md)  
  
  
