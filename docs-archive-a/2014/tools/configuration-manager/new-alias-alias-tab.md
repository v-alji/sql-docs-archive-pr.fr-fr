---
title: Nouvel alias (onglet alias) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604785"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="9810d-102">Nouvel alias (onglet Alias)</span><span class="sxs-lookup"><span data-stu-id="9810d-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="9810d-103">Un alias est un nom de remplacement permettant d'établir une connexion.</span><span class="sxs-lookup"><span data-stu-id="9810d-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="9810d-104">L'alias encapsule les éléments requis d'une chaîne de connexion, puis les expose sous un nom choisi par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9810d-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="9810d-105">La page **Alias** de la boîte de dialogue **Alias - Nouveau** vous permet de spécifier les éléments de la chaîne de connexion d’un alias.</span><span class="sxs-lookup"><span data-stu-id="9810d-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="9810d-106">Pour modifier la chaîne de connexion d’un alias existant, consultez [Propriétés de &#60;Alias&#62; &#40;onglet Alias&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="9810d-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="9810d-107">Il n'est pas nécessaire de renseigner toutes les valeurs de la grille **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="9810d-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="9810d-108">Le protocole sélectionné détermine les combinaisons valides.</span><span class="sxs-lookup"><span data-stu-id="9810d-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="9810d-109">Voir les rubriques indiquées ci-après pour obtenir des exemples de combinaisons valides.</span><span class="sxs-lookup"><span data-stu-id="9810d-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="9810d-110">**Nom de l'alias**</span><span class="sxs-lookup"><span data-stu-id="9810d-110">**Alias Name**</span></span>  
 <span data-ttu-id="9810d-111">Nom (alias) à utiliser pour faire référence à cette connexion.</span><span class="sxs-lookup"><span data-stu-id="9810d-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="9810d-112">**Nom du canal** / **Numéro de port**</span><span class="sxs-lookup"><span data-stu-id="9810d-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="9810d-113">Éléments supplémentaires de la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="9810d-113">Additional elements of the connection string.</span></span> <span data-ttu-id="9810d-114">Le nom de cette zone varie en fonction du protocole sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9810d-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="9810d-115">**Protocole**</span><span class="sxs-lookup"><span data-stu-id="9810d-115">**Protocol**</span></span>  
 <span data-ttu-id="9810d-116">Protocole utilisé pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="9810d-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="9810d-117">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="9810d-117">**Server**</span></span>  
 <span data-ttu-id="9810d-118">Nom de l’instance [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers laquelle la connexion est établie.</span><span class="sxs-lookup"><span data-stu-id="9810d-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="9810d-119">Cas d'utilisation d'un alias</span><span class="sxs-lookup"><span data-stu-id="9810d-119">When to Use an Alias</span></span>  
 <span data-ttu-id="9810d-120">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se connecte à une instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en utilisant le protocole de **mémoire partagée** , et à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un autre ordinateur à l’aide du protocole **TCP/IP** ou de **Canaux nommés**.</span><span class="sxs-lookup"><span data-stu-id="9810d-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="9810d-121">Créez un alias lorsque vous utilisez le protocole TCP/IP ou des canaux nommés, et que vous souhaitez fournir une chaîne de connexion personnalisée ou utiliser un nom différent du nom de serveur pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="9810d-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="9810d-122">Exemples</span><span class="sxs-lookup"><span data-stu-id="9810d-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9810d-123">n’étant pas à l’écoute sur le port TCP/IP 1433 par défaut, vous pouvez fournir une chaîne de connexion comportant un numéro de port différent.</span><span class="sxs-lookup"><span data-stu-id="9810d-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9810d-124">n'étant pas à l'écoute sur le canal nommé par défaut, vous pouvez fournir une chaîne de connexion comportant un nom de canal différent.</span><span class="sxs-lookup"><span data-stu-id="9810d-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="9810d-125">Une application doit normalement se connecter à une base de données située sur le serveur nommé `ACCT`, mais cette base de données a été consolidée sous la forme d'une instance nommée `ACCT` sur un serveur nommé `CENTRAL`.</span><span class="sxs-lookup"><span data-stu-id="9810d-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="9810d-126">L'application ne peut pas être facilement modifiée.</span><span class="sxs-lookup"><span data-stu-id="9810d-126">The application cannot easily be changed.</span></span> <span data-ttu-id="9810d-127">Créez un alias nommé `ACCT`, avec une chaîne de connexion pointant vers `CENTRAL\ACCT`.</span><span class="sxs-lookup"><span data-stu-id="9810d-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="9810d-128">Création d'une chaîne de connexion valide</span><span class="sxs-lookup"><span data-stu-id="9810d-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="9810d-129">Les rubriques suivantes décrivent et illustrent des combinaisons valides de propriétés d'alias :</span><span class="sxs-lookup"><span data-stu-id="9810d-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="9810d-130">Création d'une chaîne de connexion valide à l'aide du protocole de mémoire partagée</span><span class="sxs-lookup"><span data-stu-id="9810d-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="9810d-131">Création d’une chaîne de connexion valide à l’aide du protocole TCP/IP</span><span class="sxs-lookup"><span data-stu-id="9810d-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="9810d-132">Création d’une chaîne de connexion valide avec des canaux nommés</span><span class="sxs-lookup"><span data-stu-id="9810d-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
