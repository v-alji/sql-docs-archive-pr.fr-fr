---
title: Gestionnaire de connexions WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610817"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="0e4b2-102">Gestionnaire de connexions WMI</span><span class="sxs-lookup"><span data-stu-id="0e4b2-102">WMI Connection Manager</span></span>
  <span data-ttu-id="0e4b2-103">Un gestionnaire de connexions WMI permet à un package d'utiliser WMI (Windows Management Instrumentation) pour gérer des informations dans un environnement d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="0e4b2-104">La tâche de service web incluse dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilise un gestionnaire de connexions WMI.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="0e4b2-105">Lorsque vous ajoutez un gestionnaire de connexions WMI à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera résolu en une connexion WMI au moment de l’exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la `Connections` collection sur le package.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="0e4b2-106">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `WMI`.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="0e4b2-107">Configuration du gestionnaire de connexions WMI</span><span class="sxs-lookup"><span data-stu-id="0e4b2-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="0e4b2-108">Vous pouvez configurer un gestionnaire de connexions WMI de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="0e4b2-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="0e4b2-109">Spécifiez le nom d'un serveur.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="0e4b2-110">Spécifiez un espace de noms sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="0e4b2-111">Sélectionnez le mode d'authentification pour la connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="0e4b2-112">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="0e4b2-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0e4b2-113">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions WMI](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0e4b2-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="0e4b2-114">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="0e4b2-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4b2-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e4b2-115">See Also</span></span>  
 <span data-ttu-id="0e4b2-116">[Tâche de service Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="0e4b2-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="0e4b2-117">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0e4b2-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
