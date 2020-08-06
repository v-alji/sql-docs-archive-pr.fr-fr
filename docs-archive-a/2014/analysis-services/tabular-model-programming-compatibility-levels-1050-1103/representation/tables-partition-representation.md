---
title: Représentation de partition (tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: b606cd63-755c-4ac0-b19b-95b5363afbdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a29f273a584f3e60c6cf6458751965158cf8704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706796"
---
# <a name="partition-representation-tabular"></a><span data-ttu-id="d2409-102">Représentation (tabulaire) d'une partition</span><span class="sxs-lookup"><span data-stu-id="d2409-102">Partition Representation (Tabular)</span></span>
  <span data-ttu-id="d2409-103">À des fins opérationnelles, une table peut être divisée en différents sous-ensembles de lignes qui une fois combinés forment la table ; chacun de ces sous-ensembles est une partition de la table.</span><span class="sxs-lookup"><span data-stu-id="d2409-103">For operational purposes, a table can be divided in different subsets of rows that when combined together form the table; each of those subsets is a partition of the table.</span></span>  
  
## <a name="partition-representation"></a><span data-ttu-id="d2409-104">Représentation d'une partition</span><span class="sxs-lookup"><span data-stu-id="d2409-104">Partition Representation</span></span>  
 <span data-ttu-id="d2409-105">En termes d'objets AMO, une représentation de partition a une relation de mappage un-à-un avec <xref:Microsoft.AnalysisServices.Partition> et aucun autre objet AMO principal n'est requis.</span><span class="sxs-lookup"><span data-stu-id="d2409-105">In terms of AMO objects a partition representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Partition> and no other main AMO objects are required</span></span>  
  
### <a name="partition-in-amo"></a><span data-ttu-id="d2409-106">Partition dans AMO</span><span class="sxs-lookup"><span data-stu-id="d2409-106">Partition in AMO</span></span>  
 <span data-ttu-id="d2409-107">Lorsque vous utilisez AMO pour gérer une partition, vous devez rechercher le groupe de mesures qui représente la table du modèle tabulaire et partir de là.</span><span class="sxs-lookup"><span data-stu-id="d2409-107">When using AMO to manage a partition in a you need to find the measure group that represents the Tabular Model table and work from there.</span></span>  
  
 <span data-ttu-id="d2409-108">L'extrait de code suivant montre comment ajouter une partition à une table de modèle tabulaire existante.</span><span class="sxs-lookup"><span data-stu-id="d2409-108">The following code snippet shows how to add a partition to an existing tabular model table.</span></span>  
  
```  
  
private void AddPartition(  
                     AMO.Cube modelCube  
                  ,  AMO.DataSource newDatasource  
                  ,  string mgName  
                  ,  string newPartitionName  
                  , string partitionSelectStatement  
                  , Boolean processPartition  
             )  
{  
    mgName = mgName.Trim();  
    newPartitionName = newPartitionName.Trim();  
    partitionSelectStatement = partitionSelectStatement.Trim();  
    //Validate Input  
    if (string.IsNullOrEmpty(newPartitionName) || string.IsNullOrWhiteSpace(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (modelCube.MeasureGroups[mgName].Partitions.ContainsName(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name already defined. Duplicated names are not allowed"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(partitionSelectStatement) || string.IsNullOrWhiteSpace(partitionSelectStatement))  
    {  
        MessageBox.Show(String.Format("Select statement cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Input validated  
    string partitionID = newPartitionName; //Using partition name as the ID  
    AMO.Partition currentPartition = new AMO.Partition(partitionID, partitionID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, partitionSelectStatement);  
    modelCube.MeasureGroups[mgName].Partitions.Add(currentPartition);  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        if (processPartition)  
        {  
            modelCube.MeasureGroups[mgName].Partitions[partitionID].Process(AMO.ProcessType.ProcessFull);  
            MessageBox.Show(String.Format("Partition successfully processed."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        }  
  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="d2409-109">Exemple AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="d2409-109">AMO2Tabular sample</span></span>  
 <span data-ttu-id="d2409-110">Toutefois, pour connaître la façon d'utiliser AMO pour créer et manipuler des représentations de partition, consultez le code source de l'exemple Objets AMO vers objets tabulaires.</span><span class="sxs-lookup"><span data-stu-id="d2409-110">However, to have an understanding on how to use AMO to create and manipulate partition representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="d2409-111">L'exemple est disponible sur Codeplex.</span><span class="sxs-lookup"><span data-stu-id="d2409-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="d2409-112">Remarque importante à propos du code : le code est fourni uniquement comme un support aux concepts logiques expliqués ici et ne doit pas être utilisé dans un environnement de production, ni à des fins autres que pédagogiques.</span><span class="sxs-lookup"><span data-stu-id="d2409-112">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
