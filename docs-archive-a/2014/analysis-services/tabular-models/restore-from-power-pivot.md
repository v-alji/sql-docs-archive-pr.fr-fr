---
title: Restaurer à partir de PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706795"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="39f77-102">Restaurer à partir de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="39f77-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="39f77-103">Utilisez la fonctionnalité Restaurer à partir de PowerPivot dans SQL Server Management Studio pour créer une nouvelle base de données model tabulaire sur une instance Analysis Services (exécution en mode tabulaire), ou restaurer une base de données existante dans un classeur PowerPivot (.xlsx).</span><span class="sxs-lookup"><span data-stu-id="39f77-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39f77-104">Le modèle de projet Importer à partir de PowerPivot dans SQL Server Data Tools fournit une fonctionnalité similaire.</span><span class="sxs-lookup"><span data-stu-id="39f77-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="39f77-105">Pour plus d’informations, consultez [Importer à partir de PowerPivot &#40;des&#41;tabulaires SSAS ](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="39f77-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="39f77-106">Lorsque vous utilisez Restaurer à partir de PowerPivot, gardez les points suivants à l'esprit :</span><span class="sxs-lookup"><span data-stu-id="39f77-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="39f77-107">Pour utiliser Restaurer à partir de PowerPivot, vous devez être connecté en tant que membre du rôle Administrateurs de serveur sur l'instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="39f77-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="39f77-108">Le compte de service de l'instance Analysis Services doit avoir des autorisations de lecture sur le classeur à partir duquel vous effectuez la restauration.</span><span class="sxs-lookup"><span data-stu-id="39f77-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="39f77-109">Par défaut, lorsque vous restaurez une base de données PowerPivot, la propriété Informations d'emprunt d'identité de source de données de la base de données model tabulaire a la valeur Par défaut, qui indique que le compte de service de l'instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="39f77-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="39f77-110">Nous vous recommandons de modifier les informations d'identification d'emprunt d'identité vers un compte d'utilisateur Windows dans les Propriétés de la base de données.</span><span class="sxs-lookup"><span data-stu-id="39f77-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="39f77-111">Pour plus d’informations, consultez [Emprunt d’identité &#40;SSAS Tabulaire&#41;](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="39f77-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="39f77-112">Les données du modèle de données PowerPivot sont copiées dans une base de données model tabulaire existante ou nouvelle sur l'instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="39f77-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="39f77-113">Si votre classeur PowerPivot contient des tables liées, elles seront recréées comme table sans source de données, comme une table créée à l'aide de l'option Coller dans une nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="39f77-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="39f77-114">Restaurer à partir de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="39f77-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="39f77-115">Dans SSMS, dans l'instance Active Directory à restaurer, cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Restaurer à partir de PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="39f77-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="39f77-116">Dans la boîte de dialogue **Restaurer à partir de PowerPivot**, dans **Source de restauration**, dans **Fichier de sauvegarde**, cliquez sur **Parcourir**, puis sélectionnez un fichier .abf ou .xslx à partir duquel effectuer la restauration.</span><span class="sxs-lookup"><span data-stu-id="39f77-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="39f77-117">Dans **Destination de la restauration**, dans **Restaurer la base de données**, tapez un nom pour une nouvelle base de données ou une base de données existante.</span><span class="sxs-lookup"><span data-stu-id="39f77-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="39f77-118">Si vous n'indiquez pas de nom, le nom du classeur est utilisé.</span><span class="sxs-lookup"><span data-stu-id="39f77-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="39f77-119">Dans **Emplacement de stockage**, cliquez sur **Parcourir**, puis sélectionnez un emplacement pour stocker la base de données.</span><span class="sxs-lookup"><span data-stu-id="39f77-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="39f77-120">Dans **Options**, conservez l'option **Inclure des informations sur la sécurité** activée.</span><span class="sxs-lookup"><span data-stu-id="39f77-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="39f77-121">Lors de la restauration à partir d'un classeur PowerPivot, ce paramètre ne s'applique pas.</span><span class="sxs-lookup"><span data-stu-id="39f77-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f77-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39f77-122">See Also</span></span>  
 <span data-ttu-id="39f77-123">[Bases de données model tabulaires &#40;&#41;SSAS tabulaire](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="39f77-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="39f77-124">Importer à partir de PowerPivot &#40;&#41;tabulaires SSAS</span><span class="sxs-lookup"><span data-stu-id="39f77-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
