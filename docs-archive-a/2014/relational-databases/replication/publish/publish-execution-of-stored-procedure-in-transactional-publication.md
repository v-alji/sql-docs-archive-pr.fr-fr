---
title: Publier l’exécution d’une procédure stockée dans une publication transactionnelle (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602051"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="fb98d-102">publier l'exécution d'une procédure stockée dans une publication transactionnelle (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="fb98d-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="fb98d-103">Spécifiez que l’exécution d’une procédure stockée (au lieu de sa seule définition) doit être publiée dans la boîte de dialogue **Propriétés de l’article - \<Article>** .</span><span class="sxs-lookup"><span data-stu-id="fb98d-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="fb98d-104">Cette boîte de dialogue est disponible dans l’Assistant Nouvelle publication et dans la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="fb98d-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="fb98d-105">Pour plus d’informations sur l’utilisation de l’Assistant et sur l’accès à la boîte de dialogue, consultez [Créer une publication](create-a-publication.md) et [Afficher et modifier les propriétés d’une publication](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fb98d-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="fb98d-106">La définition de la procédure (l'instruction CREATE PROCEDURE) est répliquée vers l'Abonné quand l'abonnement est initialisé ; quand la procédure est exécutée sur le serveur de publication, la réplication exécute la procédure correspondante sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="fb98d-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="fb98d-107">Pour publier l'exécution d'une procédure stockée</span><span class="sxs-lookup"><span data-stu-id="fb98d-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="fb98d-108">Dans la page **Articles** de l’Assistant Nouvelle publication ou dans la boîte de dialogue **Propriétés de la publication - \<Publication>** , sélectionnez une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="fb98d-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="fb98d-109">Cliquez sur **Propriétés de l'article**, puis sur **Définir les propriétés de la procédure stockée en surbrillance**.</span><span class="sxs-lookup"><span data-stu-id="fb98d-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="fb98d-110">Dans la boîte de dialogue **Propriétés de l’article - \<Article>** , spécifiez une des valeurs suivantes pour l’option **Répliquer** :</span><span class="sxs-lookup"><span data-stu-id="fb98d-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="fb98d-111">**Exécution de la procédure stockée**</span><span class="sxs-lookup"><span data-stu-id="fb98d-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="fb98d-112">**Exécution de la procédure stockée dans une transaction sérialisée**</span><span class="sxs-lookup"><span data-stu-id="fb98d-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="fb98d-113">Cette option est recommandée car elle réplique l'exécution de la procédure uniquement si la procédure est exécutée dans le cadre d'une transaction sérialisée.</span><span class="sxs-lookup"><span data-stu-id="fb98d-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="fb98d-114">Si la procédure stockée est exécutée hors d'une transaction sérialisée, les modifications apportées aux données des tables publiées sont répliquées en tant que séries d'instructions DML (Data Manipulation Language).</span><span class="sxs-lookup"><span data-stu-id="fb98d-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="fb98d-115">Si vous êtes dans la boîte de dialogue **Propriétés de la publication - \<Publication>** , cliquez sur **OK** pour enregistrer et fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="fb98d-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb98d-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb98d-116">See Also</span></span>  
 [<span data-ttu-id="fb98d-117">Publication de l’exécution de procédures stockées dans la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="fb98d-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
