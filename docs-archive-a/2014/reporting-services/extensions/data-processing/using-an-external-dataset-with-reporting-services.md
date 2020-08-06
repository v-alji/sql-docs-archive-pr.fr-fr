---
title: Utilisation d’un jeu de données externe avec Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- DataSet objects [Reporting Services]
- data processing extensions [Reporting Services], custom DataSet objects
- custom DataSet objects [Reporting Services]
- external DataSet objects [Reporting Services]
ms.assetid: 11daa013-ec17-4760-80e3-6d84cd8d5722
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f41ba4461386e235cefe66819318106d0e72904
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708936"
---
# <a name="using-an-external-dataset-with-reporting-services"></a><span data-ttu-id="ef613-102">Utilisation d'un dataset externe avec Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ef613-102">Using an External Dataset with Reporting Services</span></span>
  <span data-ttu-id="ef613-103">L’objet **DataSet** joue un rôle essentiel dans la prise en charge de scénarios de données déconnectés et distribués avec [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef613-103">The **DataSet** object is central to supporting disconnected, distributed data scenarios with [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span></span> <span data-ttu-id="ef613-104">L’objet **DataSet** est une représentation résidant en mémoire de données qui fournit un modèle de programmation relationnel cohérent indépendamment de la source de données.</span><span class="sxs-lookup"><span data-stu-id="ef613-104">The **DataSet** object is a memory-resident representation of data that provides a consistent relational programming model regardless of the data source.</span></span> <span data-ttu-id="ef613-105">Il peut être utilisé avec plusieurs sources de données différentes, avec des données XML ou pour gérer des données locales à l'application.</span><span class="sxs-lookup"><span data-stu-id="ef613-105">It can be used with multiple different data sources, with XML data, or to manage data local to the application.</span></span> <span data-ttu-id="ef613-106">L’objet **DataSet** représente un jeu complet de données, y compris des tables associées, des contraintes et des relations entre les tables.</span><span class="sxs-lookup"><span data-stu-id="ef613-106">The **DataSet** object represents a complete set of data, including related tables, constraints, and relationships among the tables.</span></span> <span data-ttu-id="ef613-107">En raison de la polyvalence de l’objet **DataSet** concernant le stockage et l’exposition des données, il est probable que vos données soient traitées et transformées en objet **DataSet** avant toute création de rapport sur ces données.</span><span class="sxs-lookup"><span data-stu-id="ef613-107">Because of the **DataSet** object's versatility in storing and exposing data, your data may often be processed and transformed into a **DataSet** object before any reporting on that data occurs.</span></span>  
  
 <span data-ttu-id="ef613-108">Avec les extensions pour le traitement des données [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vous pouvez intégrer n’importe quel objet **DataSet** personnalisé ayant été créé par des applications externes.</span><span class="sxs-lookup"><span data-stu-id="ef613-108">With [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions, you can integrate any custom **DataSet** objects that are created by external applications.</span></span> <span data-ttu-id="ef613-109">Pour ce faire, vous créez une extension pour le traitement des données personnalisée dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] qui agit comme un pont entre votre objet **DataSet** et le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ef613-109">To accomplish this, you create a custom data processing extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] that acts like a bridge between your **DataSet** object and the report server.</span></span> <span data-ttu-id="ef613-110">La majeure partie du code nécessaire pour traiter cet objet **DataSet** est contenue dans la classe **DataReader** que vous créez.</span><span class="sxs-lookup"><span data-stu-id="ef613-110">Most of the code for processing this **DataSet** object is contained in the **DataReader** class that you create.</span></span>  
  
 <span data-ttu-id="ef613-111">La première étape à suivre pour exposer votre objet **DataSet** au serveur de rapports consiste à implémenter une méthode spécifique au fournisseur dans votre classe **DataReader** capable de remplir un objet **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="ef613-111">The first step in exposing your **DataSet** object to the report server is to implement a provider specific method in your **DataReader** class that can populate a **DataSet** object.</span></span> <span data-ttu-id="ef613-112">L’exemple suivant indique comment charger des données statiques dans un objet **DataSet** en utilisant une méthode spécifique du fournisseur dans votre classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="ef613-112">The following example shows how to load static data into a **DataSet** object by using a provider-specific method in your **DataReader** class.</span></span>  
  
```vb  
'Private members of the DataReader class  
Private m_dataSet As System.Data.DataSet  
Private m_currentRow As Integer  
  
'Method to create a dataset  
Friend Sub CreateDataSet()  
   ' Create a dataset.  
   Dim ds As New System.Data.DataSet("myDataSet")  
   ' Create a data table.   
   Dim dt As New System.Data.DataTable("myTable")  
   ' Create a data column and set various properties.   
   Dim dc As New System.Data.DataColumn()  
   dc.DataType = System.Type.GetType("System.Decimal")  
   dc.AllowDBNull = False  
   dc.Caption = "Number"  
   dc.ColumnName = "Number"  
   dc.DefaultValue = 25  
   ' Add the column to the table.   
   dt.Columns.Add(dc)  
   ' Add 10 rows and set values.   
   Dim dr As System.Data.DataRow  
   Dim i As Integer  
   For i = 0 To 9  
      dr = dt.NewRow()  
      dr("Number") = i + 1  
      ' Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr)  
   Next i  
  
   ' Fill the dataset.  
   ds.Tables.Add(dt)  
  
   ' Use a private variable to store the dataset in your  
   ' DataReader.  
   m_dataSet = ds  
  
   ' Set the current row to -1.  
   m_currentRow = - 1  
End Sub 'CreateDataSet  
```  
  
```csharp  
// Private members of the DataReader class  
private System.Data.DataSet m_dataSet;  
private int m_currentRow;  
  
// Method to create a dataset  
internal void CreateDataSet()  
{  
   // Create a dataset.  
   System.Data.DataSet ds = new System.Data.DataSet("myDataSet");  
   // Create a data table.   
   System.Data.DataTable dt = new System.Data.DataTable("myTable");  
   // Create a data column and set various properties.   
   System.Data.DataColumn dc = new System.Data.DataColumn();   
   dc.DataType = System.Type.GetType("System.Decimal");   
   dc.AllowDBNull = false;   
   dc.Caption = "Number";   
   dc.ColumnName = "Number";   
   dc.DefaultValue = 25;   
   // Add the column to the table.   
   dt.Columns.Add(dc);   
   // Add 10 rows and set values.   
   System.Data.DataRow dr;   
   for(int i = 0; i < 10; i++)  
   {   
      dr = dt.NewRow();   
      dr["Number"] = i + 1;   
      // Be sure to add the new row to the DataRowCollection.   
      dt.Rows.Add(dr);  
   }  
  
   // Fill the dataset.  
   ds.Tables.Add(dt);  
  
   // Use a private variable to store the dataset in your  
   // DataReader.  
   m_dataSet = ds;  
  
   // Set the current row to -1.  
   m_currentRow = -1;  
}  
```  
  
```csharp  
public bool Read()  
{  
   m_currentRow++;  
   if (m_currentRow >= m_dataSet.Tables[0].Rows.Count)   
   {  
      return (false);  
   }   
   else   
   {  
      return (true);  
   }  
}  
  
public int FieldCount  
{  
   // Return the count of the number of columns, which in  
   // this case is the size of the column metadata  
   // array.  
   get { return m_dataSet.Tables[0].Columns.Count; }  
}  
  
public string GetName(int i)  
{  
   return m_dataSet.Tables[0].Columns[i].ColumnName;  
}  
  
public Type GetFieldType(int i)  
{  
   // Return the actual Type class for the data type.  
   return m_dataSet.Tables[0].Columns[i].DataType;  
}  
  
public Object GetValue(int i)  
{  
   return m_dataSet.Tables[0].Rows[m_currentRow][i];  
}  
  
public int GetOrdinal(string name)  
{  
   // Look for the ordinal of the column with the same name and return it.  
   // Returns -1 if not found.  
   return m_dataSet.Tables[0].Columns[name].Ordinal;  
}  
```  
  
 <span data-ttu-id="ef613-113">Après avoir créé ou récupéré votre dataset, vous pouvez utiliser l’objet **DataSet** dans vos implémentations des membres **Read**, **GetValue**, **GetName**, **GetOrdinal**, **GetFieldType**, et **FieldCount** de la classe **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="ef613-113">Once you create or retrieve your dataset, you can use the **DataSet** object in your implementations of the **Read**, **GetValue**, **GetName**, **GetOrdinal**, **GetFieldType**, and **FieldCount** members of the **DataReader** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef613-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef613-114">See Also</span></span>  
 <span data-ttu-id="ef613-115">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="ef613-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="ef613-116">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="ef613-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="ef613-117">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ef613-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
