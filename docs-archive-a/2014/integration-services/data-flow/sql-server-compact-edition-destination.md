---
title: Destination SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfeb0bfce54c9ebefb5c526656be6b736dc0d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613066"
---
# <a name="sql-server-compact-edition-destination"></a><span data-ttu-id="ed752-102">Destination SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="ed752-102">SQL Server Compact Edition Destination</span></span>
  <span data-ttu-id="ed752-103">La destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact écrit des données dans des bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="ed752-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination writes data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact databases.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed752-104">Sur un ordinateur 64 bits, vous devez exécuter les packages qui se connectent à des sources de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact en mode 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ed752-104">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="ed752-105">Le fournisseur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact utilisé par [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour se connecter à des sources de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact n’est disponible qu’en version 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ed752-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
 <span data-ttu-id="ed752-106">Vous configurez la destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact en spécifiant le nom de la table dans laquelle la destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact insère les données.</span><span class="sxs-lookup"><span data-stu-id="ed752-106">You configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination by specifying the name of the table into which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination inserts the data.</span></span> <span data-ttu-id="ed752-107">La propriété personnalisée TableName de la destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact contient le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="ed752-107">The custom property TableName of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination contains the table name.</span></span>  
  
 <span data-ttu-id="ed752-108">Cette destination utilise un gestionnaire de connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact pour se connecter à une source de données et le gestionnaire de connexions indique le fournisseur OLE DB à utiliser.</span><span class="sxs-lookup"><span data-stu-id="ed752-108">This destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="ed752-109">Pour plus d’informations, consultez [Gestionnaire de connexions de SQL Server Compact Edition](../connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ed752-109">For more information, see [SQL Server Compact Edition Connection Manager](../connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
 <span data-ttu-id="ed752-110">La destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact comporte la propriété personnalisée TableName qui peut être mise à jour par une expression de la propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="ed752-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination includes the TableName custom property, which can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="ed752-111">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Expressions de propriété dans des packages](../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées de la destination SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ed752-111">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [SQL Server Compact Edition Destination Custom Properties](sql-server-compact-edition-destination-custom-properties.md).</span></span>  
  
 <span data-ttu-id="ed752-112">La destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact comporte une entrée et ne prend pas en charge les sorties d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="ed752-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination has one input and does not support an error output.</span></span>  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a><span data-ttu-id="ed752-113">Configuration de la destination SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="ed752-113">Configuration of the SQL Server Compact Edition Destination</span></span>  
 <span data-ttu-id="ed752-114">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="ed752-114">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ed752-115">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="ed752-115">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="ed752-116">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed752-116">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ed752-117">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="ed752-117">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="ed752-118">Propriétés personnalisées de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed752-118">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="ed752-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ed752-119">Related Tasks</span></span>  
 <span data-ttu-id="ed752-120">Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ed752-120">For more information about how to set properties of this component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed752-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed752-121">See Also</span></span>  
 [<span data-ttu-id="ed752-122">Flux de données</span><span class="sxs-lookup"><span data-stu-id="ed752-122">Data Flow</span></span>](data-flow.md)  
  
  
