---
title: Ajouter et supprimer des articles dans une publication (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7af1cac1f3ee8ecc9cb79632f8a4ef1e66ec82f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614522"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a><span data-ttu-id="696b3-102">Ajouter et supprimer des articles dans une publication (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="696b3-102">Add Articles to and Drop Articles from a Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="696b3-103">Ajoutez initialement des articles à une publication quand vous la créez dans l'Assistant Nouvelle Publication.</span><span class="sxs-lookup"><span data-stu-id="696b3-103">Initially add articles to a publication when you create it in the New Publication Wizard.</span></span> <span data-ttu-id="696b3-104">Pour plus d’informations sur l’utilisation de cet Assistant, consultez [Créer une publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="696b3-104">For more information about using this wizard, see [Create a Publication](create-a-publication.md).</span></span>  
  
 <span data-ttu-id="696b3-105">Après la création d’une publication, vous pouvez ajouter et supprimer des articles sur la page **Articles** de la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="696b3-105">After a publication is created, add and delete articles on the **Articles** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="696b3-106">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="696b3-106">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="696b3-107">Pour plus d’informations sur l’ajout et la suppression d’articles, consultez [Ajouter et supprimer des articles de publications existantes](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="696b3-107">For information about the considerations for adding and dropping articles, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a><span data-ttu-id="696b3-108">Pour ajouter un article après la création d'une publication</span><span class="sxs-lookup"><span data-stu-id="696b3-108">To add an article after a publication is created</span></span>  
  
1.  <span data-ttu-id="696b3-109">Sur la page **Articles** de la boîte de dialogue **Propriétés de publication - \<Publication>** , décochez la case **Afficher uniquement les objets activés dans la liste**.</span><span class="sxs-lookup"><span data-stu-id="696b3-109">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the **Show only checked objects in the list** check box.</span></span> <span data-ttu-id="696b3-110">Ceci vous permet de voir les objets non publiés de la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="696b3-110">This allows you to see the unpublished objects in the publication database.</span></span>  
  
2.  <span data-ttu-id="696b3-111">Activez la case à cocher en regard des articles que vous voulez ajouter.</span><span class="sxs-lookup"><span data-stu-id="696b3-111">Select the check box next to each article you want to add.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a><span data-ttu-id="696b3-112">Pour supprimer un article</span><span class="sxs-lookup"><span data-stu-id="696b3-112">To delete an article</span></span>  
  
1.  <span data-ttu-id="696b3-113">Sur la page **Articles** de la boîte de dialogue **Propriétés de publication - \<Publication>** , décochez la case en regard des articles à supprimer.</span><span class="sxs-lookup"><span data-stu-id="696b3-113">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the check box next to each article you want to delete.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="696b3-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="696b3-114">See Also</span></span>  
 <span data-ttu-id="696b3-115">[Define an Article](define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="696b3-115">[Define an Article](define-an-article.md) </span></span>  
 [<span data-ttu-id="696b3-116">Publier des données et des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="696b3-116">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
