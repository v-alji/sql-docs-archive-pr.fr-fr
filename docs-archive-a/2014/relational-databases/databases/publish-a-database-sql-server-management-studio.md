---
title: Publier une base de données (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604547"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="21a28-102">Publier une base de données (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="21a28-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="21a28-103">Vous pouvez utiliser l' **Assistant Générer et publier des scripts** pour publier une base de données entière ou des objets de base de données individuels sur un fournisseur d'hébergement Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21a28-104">Les fonctionnalités décrites dans cette rubrique étaient fournies par l'Assistant Publication de base de données.</span><span class="sxs-lookup"><span data-stu-id="21a28-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="21a28-105">La fonctionnalité de publication a été ajoutée à l'Assistant Générer et publier des scripts, et l'Assistant Publication de base de données a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="21a28-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="21a28-106">Assistant Générer et publier des scripts</span><span class="sxs-lookup"><span data-stu-id="21a28-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="21a28-107">L'Assistant Générer et publier des scripts peut être utilisé pour publier une base de données ou des objets de base de données sélectionnés sur un fournisseur d'hébergement Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="21a28-108">Un fournisseur d'hébergement Web SQL Server est une interface de connectivité vers un service Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="21a28-109">Le service Web est créé à l'aide du projet Database Publishing Services depuis le SQL Server Hosting Toolkit sur CodePlex.</span><span class="sxs-lookup"><span data-stu-id="21a28-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="21a28-110">Le service Web permet aux clients de l'hébergeur Web de publier plus facilement leurs bases de données sur le service à l'aide de l'Assistant Générer et publier des scripts.</span><span class="sxs-lookup"><span data-stu-id="21a28-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="21a28-111">Pour plus d'informations sur le téléchargement du SQL Server Hosting Toolkit, consultez [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="21a28-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="21a28-112">L'Assistant Générer et publier des scripts peut également être utilisé pour créer un script pour le transfert d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="21a28-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="21a28-113">Pour publier une base de données sur un service Web</span><span class="sxs-lookup"><span data-stu-id="21a28-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="21a28-114">Dans l’Explorateur d’objets, développez **Bases de données**, cliquez avec le bouton droit sur une base de données, pointez sur **Tâches**et cliquez sur **Générer et publier des scripts**.</span><span class="sxs-lookup"><span data-stu-id="21a28-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="21a28-115">Exécutez les étapes de l'Assistant pour générer un script pour la publication des objets de la base de données.</span><span class="sxs-lookup"><span data-stu-id="21a28-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="21a28-116">Dans la page **Sélectionner les objets** , sélectionnez les objets à publier sur le service d'hébergement Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="21a28-117">Dans la page **Définir les options de script** , sélectionnez **Publier sur le service Web**.</span><span class="sxs-lookup"><span data-stu-id="21a28-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="21a28-118">Dans la zone **Fournisseur** , spécifiez le fournisseur de votre service Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="21a28-119">Si vous n'avez pas configuré de fournisseur d'hébergement Web, sélectionnez **Gérer les fournisseurs** et utilisez la boîte de dialogue **Gérer les fournisseurs** pour configurer un fournisseur pour votre service Web.</span><span class="sxs-lookup"><span data-stu-id="21a28-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="21a28-120">Pour spécifier des options d'édition avancées, sélectionnez le bouton **Avancé** dans la section **Publier sur le service Web** .</span><span class="sxs-lookup"><span data-stu-id="21a28-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="21a28-121">Dans la page **Résumé** , vérifiez vos sélections.</span><span class="sxs-lookup"><span data-stu-id="21a28-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="21a28-122">Cliquez sur **Précédent** pour modifier vos sélections.</span><span class="sxs-lookup"><span data-stu-id="21a28-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="21a28-123">Cliquez sur **Suivant** pour publier les objets que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="21a28-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="21a28-124">Dans la page **Enregistrer ou publier des scripts** , surveillez la progression de la publication.</span><span class="sxs-lookup"><span data-stu-id="21a28-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a28-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21a28-125">See Also</span></span>  
 <span data-ttu-id="21a28-126">[Générer des scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="21a28-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="21a28-127">Copier des bases de données sur d’autres serveurs</span><span class="sxs-lookup"><span data-stu-id="21a28-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
