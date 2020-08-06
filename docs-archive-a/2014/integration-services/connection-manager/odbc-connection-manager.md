---
title: Gestionnaire de connexions ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604081"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="86575-102">Gestionnaire de connexions ODBC</span><span class="sxs-lookup"><span data-stu-id="86575-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="86575-103">Un gestionnaire de connexions ODBC permet à un package de se connecter à divers systèmes de gestion de base de données à l'aide de la spécification ODBC (Open Database Connectivity).</span><span class="sxs-lookup"><span data-stu-id="86575-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="86575-104">Lorsque vous ajoutez une connexion ODBC à un package et définissez les propriétés du gestionnaire de connexions, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions et ajoute le gestionnaire de connexions à la `Connections` collection du package.</span><span class="sxs-lookup"><span data-stu-id="86575-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="86575-105">Au moment de l'exécution, le gestionnaire de connexions est résolu en tant que connexion ODBC physique.</span><span class="sxs-lookup"><span data-stu-id="86575-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="86575-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `ODBC`.</span><span class="sxs-lookup"><span data-stu-id="86575-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="86575-107">Vous pouvez configurer le gestionnaire de connexions ODBC de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="86575-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="86575-108">Fournissez une chaîne de connexion qui fait référence à un nom d'utilisateur ou de source de données système.</span><span class="sxs-lookup"><span data-stu-id="86575-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="86575-109">Spécifiez le serveur auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="86575-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="86575-110">Indiquez si la connexion est conservée au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="86575-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="86575-111">Configuration du gestionnaire de connexions ODBC</span><span class="sxs-lookup"><span data-stu-id="86575-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="86575-112">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="86575-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="86575-113">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="86575-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="86575-114">Informations de référence sur l’interface utilisateur du gestionnaire de connexions ODBC</span><span class="sxs-lookup"><span data-stu-id="86575-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="86575-115">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="86575-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86575-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86575-116">See Also</span></span>  
 [<span data-ttu-id="86575-117">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="86575-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
