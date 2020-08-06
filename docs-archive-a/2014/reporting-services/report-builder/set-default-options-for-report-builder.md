---
title: Boîte de dialogue Options de Générateur de rapports, paramètres (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 07bd4a7f9dfe1abd8ab76765cb1ac10ff5227066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602768"
---
# <a name="report-builder-options-dialog-box-settings-report-builder"></a><span data-ttu-id="94e0b-102">Boîte de dialogue Options du Générateur de rapports, Paramètres (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="94e0b-102">Report Builder Options Dialog Box, Settings (Report Builder)</span></span>
  <span data-ttu-id="94e0b-103">Cliquez sur le bouton **Générateur de rapports** , puis sur **options** pour définir les options d’indication des fichiers et des connexions récents.</span><span class="sxs-lookup"><span data-stu-id="94e0b-103">Click the **Report Builder** button and then click **Options** to set options for showing recent files and connections.</span></span> <span data-ttu-id="94e0b-104">Vous pouvez également modifier le serveur de rapports par défaut ou en ajouter un si vous n'en avez pas déjà spécifié un.</span><span class="sxs-lookup"><span data-stu-id="94e0b-104">You can also change the default report server, or add one if you don't have a default.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="94e0b-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="94e0b-105">UI element list</span></span>  
 <span data-ttu-id="94e0b-106">**Utiliser ce serveur de rapports ou site SharePoint par défaut**</span><span class="sxs-lookup"><span data-stu-id="94e0b-106">**Use this report server or SharePoint site by default**</span></span>  
 <span data-ttu-id="94e0b-107">Il se peut que votre administrateur ait configuré ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="94e0b-107">Your administrator may have configured this.</span></span> <span data-ttu-id="94e0b-108">Sa valeur peut être une URL bien formée commençant par http:// ou https://.</span><span class="sxs-lookup"><span data-stu-id="94e0b-108">The value can be a well-formed URL starting with http:// or https://.</span></span> <span data-ttu-id="94e0b-109">Ce paramètre détermine les connexions de source de données qui s'affichent par défaut dans les Assistants Tableau/Matrice et Graphique.</span><span class="sxs-lookup"><span data-stu-id="94e0b-109">This setting determines which data source connections appear by default in the Table/Matrix and Chart wizards.</span></span> <span data-ttu-id="94e0b-110">Sachez par ailleurs que vos rapports seront traités sur ce serveur et que vous pouvez faire référence à des ressources provenant de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="94e0b-110">In addition, your reports will be processed on this server and you can reference resources from this server.</span></span>  
  
 <span data-ttu-id="94e0b-111">Si vous sélectionnez un autre serveur de rapports, vous serez peut-être amené à redémarrer le Générateur de rapports pour que cette modification soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="94e0b-111">If you select a different report server, you may need to restart Report Builder in order for this change to take affect.</span></span>  
  
 <span data-ttu-id="94e0b-112">**Publier des parties de rapport dans ce dossier par défaut**</span><span class="sxs-lookup"><span data-stu-id="94e0b-112">**Publish report parts to this folder by default**</span></span>  
 <span data-ttu-id="94e0b-113">Le Générateur de rapports enregistre les parties de rapport que vous publiez dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="94e0b-113">Report Builder will save report parts that you publish to this folder.</span></span> <span data-ttu-id="94e0b-114">Si le dossier n'existe pas encore et que vous êtes autorisé à créer des dossiers sur le serveur de rapports, le Générateur de rapports crée ce dossier.</span><span class="sxs-lookup"><span data-stu-id="94e0b-114">If the folder does not exist yet and you have permissions to create folders on the report server, Report Builder will create this folder.</span></span>  
  
 <span data-ttu-id="94e0b-115">Vous n'avez pas à redémarrer le Générateur de rapports pour que ce paramètre entre en vigueur.</span><span class="sxs-lookup"><span data-stu-id="94e0b-115">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
 <span data-ttu-id="94e0b-116">**Afficher ce nombre de serveurs et de sites récents**</span><span class="sxs-lookup"><span data-stu-id="94e0b-116">**Show this number of recent sites and servers**</span></span>  
 <span data-ttu-id="94e0b-117">Spécifiez le nombre de connexions et de sites récents à afficher dans les boîtes de dialogue **Ouvrir le rapport** et **Enregistrer comme rapport** .</span><span class="sxs-lookup"><span data-stu-id="94e0b-117">Specify the number of recent sites and connections to show in the **Open Report** and **Save As Report** dialog boxes.</span></span>  
  
 <span data-ttu-id="94e0b-118">**Afficher ce nombre de datasets et de connexions à la source de données récents partagés**</span><span class="sxs-lookup"><span data-stu-id="94e0b-118">**Show this number of recent shared datasets and data source connections**</span></span>  
 <span data-ttu-id="94e0b-119">Spécifiez le nombre de datasets et de connexions à la source de données récents partagés à afficher dans la boîte de dialogue **Propriétés du dataset** et dans la page **Choisir une connexion à une source de données** de l’Assistant Régions de données.</span><span class="sxs-lookup"><span data-stu-id="94e0b-119">Specify the number of recent shared datasets and data source connections to show in the **Dataset Properties** dialog box and the **Choose a connection to a data source** page of the Data Regions Wizard.</span></span>  
  
 <span data-ttu-id="94e0b-120">**Afficher ce nombre de documents récents**</span><span class="sxs-lookup"><span data-stu-id="94e0b-120">**Show this number of recent documents**</span></span>  
 <span data-ttu-id="94e0b-121">Spécifiez le nombre de documents récents à afficher lorsque vous cliquez sur le bouton Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="94e0b-121">Specify the number of recent documents to show when you click the Report Builder button.</span></span>  
  
 <span data-ttu-id="94e0b-122">**Effacer toutes les listes d'éléments récentes**</span><span class="sxs-lookup"><span data-stu-id="94e0b-122">**Clear all recent item lists**</span></span>  
 <span data-ttu-id="94e0b-123">Effacez les listes actuelles de serveurs et de sites récents, de documents, de datasets partagés et de connexions à des sources de données partagées.</span><span class="sxs-lookup"><span data-stu-id="94e0b-123">Clear the current lists of recent sites and servers, shared datasets, shared data source connections, and documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e0b-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94e0b-124">See Also</span></span>  
 [<span data-ttu-id="94e0b-125">Aide du Générateur de rapports pour les boîtes de dialogue, les volets et les Assistants</span><span class="sxs-lookup"><span data-stu-id="94e0b-125">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
