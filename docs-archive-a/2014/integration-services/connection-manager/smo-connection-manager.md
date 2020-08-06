---
title: Gestionnaire de connexions SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 988eef214608399bc3ec483d9976c2f5d52acb2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708551"
---
# <a name="smo-connection-manager"></a><span data-ttu-id="68886-102">Gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="68886-102">SMO Connection Manager</span></span>
  <span data-ttu-id="68886-103">Un gestionnaire de connexions SMO permet à un package de se connecter à un serveur SMO (SQL Management Object).</span><span class="sxs-lookup"><span data-stu-id="68886-103">An SMO connection manager enables a package to connect to a SQL Management Object (SMO) server.</span></span> <span data-ttu-id="68886-104">Les tâches de transfert incluses dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilisent un gestionnaire de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="68886-104">The transfer tasks that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes use an SMO connection manager.</span></span> <span data-ttu-id="68886-105">Par exemple, la tâche de transfert de connexions qui transfère des connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilise un gestionnaire de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="68886-105">For example, the Transfer Logins task that transfers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins uses an SMO connection manager.</span></span>  
  
 <span data-ttu-id="68886-106">Lorsque vous ajoutez un gestionnaire de connexions SMO à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera résolu en tant que connexion SMO au moment de l'exécution, définit les propriétés du gestionnaire de connexions et ajoute le gestionnaire de connexions à la collection `Connections` sur le package.</span><span class="sxs-lookup"><span data-stu-id="68886-106">When you add an SMO connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="68886-107">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `SMOServer`.</span><span class="sxs-lookup"><span data-stu-id="68886-107">The `ConnectionManagerType` property of the connection manager is set to `SMOServer`.</span></span>  
  
 <span data-ttu-id="68886-108">Vous pouvez configurer le gestionnaire de connexions SMO de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="68886-108">You can configure an SMO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="68886-109">Spécifiez le nom d'un serveur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="68886-109">Specify the name of a server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="68886-110">Sélectionnez le mode d'authentification pour la connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="68886-110">Select the authentication mode for connecting to the server.</span></span>  
  
## <a name="configuration-of-the-smo-connection-manager"></a><span data-ttu-id="68886-111">Configuration du gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="68886-111">Configuration of the SMO Connection Manager</span></span>  
 <span data-ttu-id="68886-112">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="68886-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="68886-113">Pour plus d’informations sur les propriétés que vous pouvez définir dans le Concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions SMO](../smo-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="68886-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMO Connection Manager Editor](../smo-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="68886-114">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="68886-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68886-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68886-115">See Also</span></span>  
 [<span data-ttu-id="68886-116">Connexions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="68886-116">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
