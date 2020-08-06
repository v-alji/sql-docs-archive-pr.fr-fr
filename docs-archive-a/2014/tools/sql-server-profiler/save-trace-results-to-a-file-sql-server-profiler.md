---
title: Enregistrer des résultats d’une trace dans un fichier (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705723"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="fb7da-102">Enregistrer des résultats d'une trace dans un fichier (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="fb7da-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="fb7da-103">Cette rubrique explique comment enregistrer les résultats d'une trace dans un fichier en utilisant le [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb7da-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="fb7da-104">Pour enregistrer les résultats d'une trace dans un fichier</span><span class="sxs-lookup"><span data-stu-id="fb7da-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="fb7da-105">Dans le menu **Fichier** , cliquez sur **Nouvelle trace**, puis connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb7da-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="fb7da-106">La boîte de dialogue **Propriétés de la trace**apparaît.</span><span class="sxs-lookup"><span data-stu-id="fb7da-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb7da-107">Si la case **Démarrer le suivi juste après avoir établi la connexion**est cochée, la boîte de dialogue **Propriétés de la trace**ne s’affiche pas et le suivi se lance.</span><span class="sxs-lookup"><span data-stu-id="fb7da-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="fb7da-108">Pour désactiver ce paramètre, accédez au menu **Outils**, cliquez sur **Options**et désactivez la case à cocher **Démarrer le suivi juste après avoir établi la connexion** .</span><span class="sxs-lookup"><span data-stu-id="fb7da-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="fb7da-109">Dans la zone **Nom de la trace** , tapez un nom pour la trace.</span><span class="sxs-lookup"><span data-stu-id="fb7da-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="fb7da-110">Cochez la case **Enregistrer dans le fichier** .</span><span class="sxs-lookup"><span data-stu-id="fb7da-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="fb7da-111">La boîte de dialogue **Enregistrer sous**s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fb7da-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="fb7da-112">Spécifiez un chemin et un nom de fichier dans la boîte de dialogue **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="fb7da-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="fb7da-113">Cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="fb7da-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb7da-114">Vérifiez que le service SQL Server dispose des autorisations suffisantes pour écrire dans un fichier dans le répertoire défini.</span><span class="sxs-lookup"><span data-stu-id="fb7da-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="fb7da-115">Dans la boîte de dialogue **Propriétés de la trace** , entrez la taille de fichier maximale dans la zone de texte **Définir la taille de fichier maximale (Mo)** .</span><span class="sxs-lookup"><span data-stu-id="fb7da-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="fb7da-116">La valeur par défaut est 5 mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="fb7da-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="fb7da-117">Vous pouvez également définir les options facultatives suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb7da-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="fb7da-118">Cochez la case **Activer la substitution de fichier** pour que [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] crée des fichiers pour les données de trace lorsque la limite de taille de fichier maximale est atteinte.</span><span class="sxs-lookup"><span data-stu-id="fb7da-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="fb7da-119">Cette option est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="fb7da-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="fb7da-120">Cochez la case **Le serveur traite les données de trace** pour que le serveur enregistre chaque événement de trace.</span><span class="sxs-lookup"><span data-stu-id="fb7da-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fb7da-121">Lorsque l’option **Le serveur traite les données de trace**est désactivée, le serveur n’enregistre pas les événements si cette opération dégrade sensiblement les performances.</span><span class="sxs-lookup"><span data-stu-id="fb7da-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7da-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb7da-122">See Also</span></span>  
 [<span data-ttu-id="fb7da-123">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="fb7da-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
