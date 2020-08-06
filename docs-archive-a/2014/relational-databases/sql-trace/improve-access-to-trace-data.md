---
title: Améliorer l’accès aux données de trace | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697655"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="07508-102">Améliorer l'accès aux données de trace</span><span class="sxs-lookup"><span data-stu-id="07508-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="07508-103">utilise l’espace du répertoire **temp** pour améliorer l’accès aux données de trace.</span><span class="sxs-lookup"><span data-stu-id="07508-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="07508-104">nécessite au moins 10 mégaoctets (Mo) d’espace libre.</span><span class="sxs-lookup"><span data-stu-id="07508-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="07508-105">Si l’espace disponible descend en dessous de 10 Mo pendant que vous utilisez [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], toutes les fonctions de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] sont interrompues.</span><span class="sxs-lookup"><span data-stu-id="07508-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="07508-106">Quand [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] utilise l’espace du répertoire **temp** , cette utilisation d’espace peut entraîner la croissance rapide du répertoire **temp** .</span><span class="sxs-lookup"><span data-stu-id="07508-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="07508-107">Pour éviter tout problème de croissance de fichier, vous pouvez placer le répertoire **temp** sur un lecteur non système en modifiant la valeur de la variable d’environnement TEMP.</span><span class="sxs-lookup"><span data-stu-id="07508-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="07508-108">La procédure ci-dessous décrit comment modifier la valeur de la variable d'environnement TEMP dans la plupart des systèmes d'exploitation Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="07508-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="07508-109">Pour plus d'informations sur la définition des variables d'environnement, consultez la documentation de votre système d'exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="07508-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="07508-110">Pour modifier la variable d'environnement TEMP dans les systèmes d'exploitation Windows</span><span class="sxs-lookup"><span data-stu-id="07508-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="07508-111">Dans le menu **Démarrer** , choisissez **Panneau de configuration**, puis cliquez sur **Système**.</span><span class="sxs-lookup"><span data-stu-id="07508-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="07508-112">Dans la boîte de dialogue **Propriétés système** , cliquez sur l’onglet **Avancé** , puis sur **Variables d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="07508-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="07508-113">Faites défiler la liste **Variables système**, sélectionnez la ligne qui correspond à la variable **TEMP** , puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="07508-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="07508-114">Dans la boîte de dialogue **Modifier la variable système** , entrez le nom et le chemin du lecteur sur lequel vous voulez placer le répertoire **temp** .</span><span class="sxs-lookup"><span data-stu-id="07508-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="07508-115">Cliquez sur **OK** pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="07508-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07508-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07508-116">See Also</span></span>  
 <span data-ttu-id="07508-117">[Démarrer SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="07508-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="07508-118">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="07508-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
