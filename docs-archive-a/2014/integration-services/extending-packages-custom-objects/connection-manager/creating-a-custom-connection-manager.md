---
title: Création d’un gestionnaire de connexions personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709775"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="33277-102">Création d'un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="33277-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="33277-103">Les étapes à suivre pour créer un gestionnaire de connexions personnalisé sont similaires à celles permettant de créer tout autre objet personnalisé pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="33277-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="33277-104">Créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="33277-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="33277-105">Pour un gestionnaire de connexions, la classe de base est <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="33277-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="33277-106">Appliquer l'attribut qui identifie le type d'objet auprès de la classe.</span><span class="sxs-lookup"><span data-stu-id="33277-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="33277-107">Pour un gestionnaire de connexions, l'attribut est <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="33277-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="33277-108">Remplacer l'implémentation des méthodes et propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="33277-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="33277-109">Pour un gestionnaire de connexions, celles-ci incluent la propriété <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> et les méthodes <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> et <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="33277-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="33277-110">Développer éventuellement une interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="33277-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="33277-111">Pour un gestionnaire de connexions, cette opération requiert une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.</span><span class="sxs-lookup"><span data-stu-id="33277-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33277-112">Une grande partie des tâches, sources et destinations intégrées à [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] utilisent uniquement des types spécifiques de gestionnaires de connexions intégrés.</span><span class="sxs-lookup"><span data-stu-id="33277-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="33277-113">Par conséquent, ces exemples ne peuvent pas être testés avec les tâches et composants intégrés.</span><span class="sxs-lookup"><span data-stu-id="33277-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="33277-114">Mise en route d'un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="33277-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="33277-115">Création de projets et de classes</span><span class="sxs-lookup"><span data-stu-id="33277-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="33277-116">Puisque tous les gestionnaires de connexions managés dérivent de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, la première étape de création d'un gestionnaire de connexions personnalisé consiste à créer un projet Bibliothèque de classes dans votre langage de programmation managé par défaut et à créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="33277-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="33277-117">Dans cette classe dérivée, vous allez substituer les méthodes et les propriétés de la classe de base pour implémenter vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="33277-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="33277-118">Dans la même solution, créez un deuxième projet Bibliothèque de classes pour l'interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="33277-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="33277-119">Il est recommandé d’utiliser un assembly distinct pour l’interface utilisateur afin de faciliter le déploiement car vous pouvez ainsi mettre à jour et redéployer le gestionnaire de connexions ou son interface utilisateur de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="33277-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="33277-120">Configurez les deux projets pour qu'ils signent les assemblys qui seront créés au moment de la génération à l'aide d'un fichier de clé de nom fort.</span><span class="sxs-lookup"><span data-stu-id="33277-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="33277-121">Application de l'attribut DtsConnection</span><span class="sxs-lookup"><span data-stu-id="33277-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="33277-122">Appliquez l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> à la classe que vous avez créée pour l'identifier en tant que gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="33277-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="33277-123">Cet attribut fournit des informations au moment de la conception, telles que le nom, la description et le type de connexion du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="33277-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="33277-124">Les <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> `Description` Propriétés et correspondent au **type** et aux `Description` colonnes affichées dans la boîte de dialogue **Ajouter un gestionnaire de connexions SSIS** , qui s’affiche lors de la configuration des connexions pour un package dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33277-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="33277-125">Utilisez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> pour lier le gestionnaire de connexions à son interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="33277-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="33277-126">Pour obtenir le jeton de clé publique requis pour cette propriété, vous pouvez utiliser **sn.exe -t** de manière à afficher le jeton de clé publique du fichier de paire de clés (.snk) que vous voulez utiliser pour signer l’assembly de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="33277-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="33277-127">Génération, déploiement et débogage d'un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="33277-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="33277-128">Les étapes permettant de générer, déployer et déboguer un gestionnaire de connexions personnalisé dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sont très similaires aux étapes requises pour les autres types d'objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="33277-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="33277-129">Pour plus d’informations, consultez [Génération, déploiement et débogage d’objets personnalisés](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="33277-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="33277-130">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="33277-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="33277-131">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="33277-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="33277-132">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="33277-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="33277-133">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="33277-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33277-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33277-134">See Also</span></span>  
 <span data-ttu-id="33277-135">[Codage d’un gestionnaire de connexions personnalisé](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="33277-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="33277-136">Développement d'une interface utilisateur pour un gestionnaire de connexions personnalisé</span><span class="sxs-lookup"><span data-stu-id="33277-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
