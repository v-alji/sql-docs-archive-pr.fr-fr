---
title: Comprendre le fournisseur WMI pour la gestion de la configuration | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599810"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="7594e-102">Présentation du fournisseur WMI pour la gestion de la configuration</span><span class="sxs-lookup"><span data-stu-id="7594e-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="7594e-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fournit le fournisseur WMI pour la gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="7594e-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="7594e-104">Cela vous permet d'utiliser WMI (Windows Management Instrumentation) pour gérer les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les paramètres réseau client et serveur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ainsi que les alias de serveur.</span><span class="sxs-lookup"><span data-stu-id="7594e-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="7594e-105">les services, les paramètres réseau et les alias sont représentés par des objets WMI dans l’espace de noms root\Microsoft\SqlServer\ComputerManagement*nn* de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7594e-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="7594e-106">Une fois qu'une connexion est établie avec le fournisseur WMI sur l'ordinateur spécifié, les services, paramètres réseau et alias peuvent être interrogés à l'aide du langage WQL ou d'un langage de script.</span><span class="sxs-lookup"><span data-stu-id="7594e-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="7594e-107">Le fournisseur WMI est un fournisseur d'instances.</span><span class="sxs-lookup"><span data-stu-id="7594e-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="7594e-108">Il fournit des instances des [classes WMI](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) et prend en charge les opérations asynchrones suivantes.</span><span class="sxs-lookup"><span data-stu-id="7594e-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="7594e-109">Récupération d'instance</span><span class="sxs-lookup"><span data-stu-id="7594e-109">Instance retrieval</span></span>  
 <span data-ttu-id="7594e-110">Récupération d'une instance spécifique d'un type de classe.</span><span class="sxs-lookup"><span data-stu-id="7594e-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="7594e-111">Énumération</span><span class="sxs-lookup"><span data-stu-id="7594e-111">Enumeration</span></span>  
 <span data-ttu-id="7594e-112">Énumération de toutes les instances d'un type de classe.</span><span class="sxs-lookup"><span data-stu-id="7594e-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="7594e-113">Modification</span><span class="sxs-lookup"><span data-stu-id="7594e-113">Modification</span></span>  
 <span data-ttu-id="7594e-114">Modification d'une instance spécifique d'un type de classe.</span><span class="sxs-lookup"><span data-stu-id="7594e-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="7594e-115">Les classes ont des méthodes qui autorisent la modification de leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="7594e-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="7594e-116">Suppression</span><span class="sxs-lookup"><span data-stu-id="7594e-116">Deletion</span></span>  
 <span data-ttu-id="7594e-117">Suppression d'une instance spécifique d'un type de classe.</span><span class="sxs-lookup"><span data-stu-id="7594e-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="7594e-118">Traitement des requêtes</span><span class="sxs-lookup"><span data-stu-id="7594e-118">Query processing</span></span>  
 <span data-ttu-id="7594e-119">Énumération des instances d'un type de classe en fonction d'un filtre.</span><span class="sxs-lookup"><span data-stu-id="7594e-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="7594e-120">Pour obtenir des exemples d’applications de gestion utilisant le fournisseur WMI pour la gestion de la configuration, consultez [utilisation des langages WQL et de script avec le fournisseur WMI pour la gestion de la configuration](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7594e-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="7594e-121">Pour plus d’informations sur la programmation d’applications de gestion à l’aide du fournisseur WMI, consultez la documentation WMI dans le [!INCLUDE[msCoName](../../includes/msconame-md.md)] Kit de développement logiciel (SDK) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7594e-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7594e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7594e-122">See Also</span></span>  
 <span data-ttu-id="7594e-123">[Utilisation du fournisseur WMI pour la gestion de la configuration](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="7594e-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="7594e-124">Utilisation des langages WQL et de script avec le fournisseur WMI pour la gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="7594e-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
