---
title: Supprimer une version (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614142"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="7884e-102">Supprimer une version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7884e-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="7884e-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], supprimez une version lorsque vous êtes sûr de ne plus avoir besoin des données de référence qui lui sont associées.</span><span class="sxs-lookup"><span data-stu-id="7884e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="7884e-104">Après avoir supprimé une version, vous ne pouvez pas récupérer les données de référence associées.</span><span class="sxs-lookup"><span data-stu-id="7884e-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7884e-105">Si un modèle a une seule version et que vous la supprimez, le modèle devient inutilisable.</span><span class="sxs-lookup"><span data-stu-id="7884e-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7884e-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="7884e-106">Prerequisites</span></span>  
 <span data-ttu-id="7884e-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="7884e-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="7884e-108">Vous devez avoir l'autorisation d'afficher la vue mdm.viw_SYSTEM_SCHEMA_VERSION et d'exécuter la procédure stockée mds.udpVersionDelete dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7884e-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="7884e-109">Pour plus d’informations, consultez [Sécurité de l’objet de base de données &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7884e-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="7884e-110">Pour supprimer une version</span><span class="sxs-lookup"><span data-stu-id="7884e-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="7884e-111">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] et connectez-vous à l’instance [!INCLUDE[ssDE](../includes/ssde-md.md)] pour votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7884e-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="7884e-112">Ouvrez la vue mdm.viw_SYSTEM_SCHEMA_VERSION.</span><span class="sxs-lookup"><span data-stu-id="7884e-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="7884e-113">Recherchez la version du modèle que vous souhaitez supprimer et copiez la valeur dans le champ **ID** .</span><span class="sxs-lookup"><span data-stu-id="7884e-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="7884e-114">Créez une requête.</span><span class="sxs-lookup"><span data-stu-id="7884e-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="7884e-115">Tapez le texte suivant, en remplaçant *ID_version* par la valeur copiée à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="7884e-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="7884e-116">Exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="7884e-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7884e-117">Vous devrez peut-être attendre quelques minutes avant que l'application Web ne reflète la modification.</span><span class="sxs-lookup"><span data-stu-id="7884e-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7884e-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7884e-118">See Also</span></span>  
 <span data-ttu-id="7884e-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="7884e-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="7884e-120">Copier une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7884e-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
