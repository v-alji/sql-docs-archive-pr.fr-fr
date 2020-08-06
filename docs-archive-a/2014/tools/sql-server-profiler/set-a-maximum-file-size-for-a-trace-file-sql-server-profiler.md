---
title: Définir la taille maximale d’un fichier de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704552"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="e2c51-102">Définir la taille maximale d'un fichier de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e2c51-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="e2c51-103">Procédez comme suit pour définir la taille maximale d'un fichier de trace.</span><span class="sxs-lookup"><span data-stu-id="e2c51-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="e2c51-104">Pour définir une taille maximale de fichier de trace</span><span class="sxs-lookup"><span data-stu-id="e2c51-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="e2c51-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2c51-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="e2c51-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="e2c51-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2c51-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="e2c51-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="e2c51-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="e2c51-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="e2c51-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="e2c51-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="e2c51-110">Dans la liste **Nom du modèle**, sélectionnez un modèle de trace.</span><span class="sxs-lookup"><span data-stu-id="e2c51-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="e2c51-111">Sélectionnez **Enregistrer dans le fichier**, puis spécifiez un fichier dans lequel stocker les informations de trace.</span><span class="sxs-lookup"><span data-stu-id="e2c51-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="e2c51-112">Dans la case à cocher **Définir la taille de fichier maximale** , spécifiez la taille de fichier maximale pour la trace.</span><span class="sxs-lookup"><span data-stu-id="e2c51-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="e2c51-113">Quand la taille du fichier atteint ce maximum, les événements de la trace ne sont plus enregistrés.</span><span class="sxs-lookup"><span data-stu-id="e2c51-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="e2c51-114">Si vous sélectionnez **Activer la substitution de fichier** (option par défaut), voici ce qu’il se produit :</span><span class="sxs-lookup"><span data-stu-id="e2c51-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="e2c51-115">L'option de substitution de fichier entraîne la fermeture par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du fichier actif et la création d'un nouveau fichier lorsque la taille de fichier maximale est atteinte.</span><span class="sxs-lookup"><span data-stu-id="e2c51-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="e2c51-116">Le nouveau fichier possède le même nom que le fichier d'origine, mais un entier est ajouté au nom pour indiquer son numéro séquentiel. Par exemple, si le premier fichier de trace s'appelle nom_fichier_1.trc, le deuxième se nommera nom_fichier_2.trc.</span><span class="sxs-lookup"><span data-stu-id="e2c51-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="e2c51-117">Si le nom attribué au nouveau fichier de substitution est celui d'un fichier existant, ce dernier est écrasé sauf s'il est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e2c51-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="e2c51-118">L’option de substitution de fichier est activée par défaut lors de l’enregistrement de données de trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="e2c51-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="e2c51-119">Lorsque l’option de substitution de fichier est activée, la trace se poursuit jusqu'à ce qu'elle soit arrêtée par un autre moyen.</span><span class="sxs-lookup"><span data-stu-id="e2c51-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="e2c51-120">Pour arrêter la trace lorsque la taille de fichier maximale est atteinte, vous devez désactiver l’option de substitution de fichier.</span><span class="sxs-lookup"><span data-stu-id="e2c51-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e2c51-121">Le système de fichiers FAT32 impose une limite maximale légèrement inférieure à 4 gigaoctets (Go) à la taille de fichier.</span><span class="sxs-lookup"><span data-stu-id="e2c51-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="e2c51-122">Lorsque la taille du fichier de trace atteint ce maximum, la trace échoue et le message d'erreur « Espace disque insuffisant » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e2c51-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="e2c51-123">Pour que des fichiers plus volumineux puissent être créés, vous devez opter pour le système de fichiers NTFS.</span><span class="sxs-lookup"><span data-stu-id="e2c51-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2c51-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2c51-124">See Also</span></span>  
 [<span data-ttu-id="e2c51-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e2c51-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
