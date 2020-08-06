---
title: Création d’une destination ODBC à l’aide du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611174"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="604d8-102">Création d'une destination ODBC à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="604d8-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="604d8-103">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], vous enregistrez généralement les données dans une destination ODBC en utilisant une destination [!INCLUDE[vstecado](../../includes/vstecado-md.md)] et le fournisseur de données [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] pour ODBC.</span><span class="sxs-lookup"><span data-stu-id="604d8-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="604d8-104">Toutefois, vous pouvez également créer une destination ODBC ad hoc à utiliser dans un package unique.</span><span class="sxs-lookup"><span data-stu-id="604d8-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="604d8-105">Pour créer cette destination ODBC ad hoc, vous utilisez le composant Script comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="604d8-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="604d8-106">Si vous souhaitez créer un composant que vous pouvez réutiliser plus facilement dans plusieurs tâches de flux de données et plusieurs packages, utilisez le code présenté dans cet exemple de composant Script comme point de départ pour un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="604d8-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="604d8-107">Pour plus d’informations, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="604d8-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="604d8-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="604d8-108">Example</span></span>  
 <span data-ttu-id="604d8-109">L’exemple suivant montre comment créer un composant de destination qui utilise un gestionnaire de connexions ODBC existant pour enregistrer des données du flux de données dans une table [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604d8-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="604d8-110">Cet exemple est une version modifiée de la destination [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personnalisée présentée dans la rubrique [Création d’une destination à l’aide du composant Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="604d8-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="604d8-111">Toutefois, dans cet exemple, la destination [!INCLUDE[vstecado](../../includes/vstecado-md.md)] personnalisée a été modifiée afin d'utiliser un gestionnaire de connexions ODBC et d'enregistrer les données dans une destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="604d8-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="604d8-112">Ces modifications incluent également les points suivants :</span><span class="sxs-lookup"><span data-stu-id="604d8-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="604d8-113">Vous ne pouvez pas appeler la méthode `AcquireConnection` du gestionnaire de connexions ODBC à partir du code managé, parce qu'elle renvoie un objet natif.</span><span class="sxs-lookup"><span data-stu-id="604d8-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="604d8-114">Par conséquent, cet exemple utilise la chaîne de connexion du gestionnaire de connexions pour se connecter directement à la source de données en utilisant le fournisseur de données [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] pour ODBC managé.</span><span class="sxs-lookup"><span data-stu-id="604d8-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="604d8-115">`OdbcCommand` attend des paramètres positionnels.</span><span class="sxs-lookup"><span data-stu-id="604d8-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="604d8-116">Les positions des paramètres sont indiquées par les points d'interrogation (?) dans le texte de la commande.</span><span class="sxs-lookup"><span data-stu-id="604d8-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="604d8-117">(Par opposition, `SqlCommand` attend des paramètres nommés.)</span><span class="sxs-lookup"><span data-stu-id="604d8-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="604d8-118">Cet exemple utilise la table **Person.Address** de l’exemple de base de données **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="604d8-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="604d8-119">L’exemple passe la première et la quatrième colonne, les colonnes **int \* AddressID**\* et **nvarchar (30) City** , de cette table dans le Workflow.</span><span class="sxs-lookup"><span data-stu-id="604d8-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="604d8-120">Ces mêmes données sont utilisées dans les exemples de sources, transformations et destinations de la rubrique [Développement de types spécifiques de composants Script](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="604d8-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="604d8-121">Pour configurer cet exemple de composant Script</span><span class="sxs-lookup"><span data-stu-id="604d8-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="604d8-122">Créez un gestionnaire de connexions ODBC qui se connecte à la base de données **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="604d8-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="604d8-123">Créez une table de destination en exécutant la commande Transact-SQL suivante dans la base de données **AdventureWorks** :</span><span class="sxs-lookup"><span data-stu-id="604d8-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="604d8-124">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que destination.</span><span class="sxs-lookup"><span data-stu-id="604d8-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="604d8-125">Connectez la sortie d'une source ou transformation en amont au composant de destination dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="604d8-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="604d8-126">(Vous pouvez connecter directement une source à une destination sans transformation.) Pour garantir le bon fonctionnement de cet exemple, la sortie du composant en amont doit inclure au moins les colonnes **AddressID** et **City** de la table **Person.Address** de l’exemple de base de données **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="604d8-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="604d8-127">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="604d8-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="604d8-128">Dans la page **Colonnes d’entrée**, sélectionnez les colonnes **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="604d8-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="604d8-129">Dans la page **Entrées et sorties**, renommez l’entrée en lui attribuant un nom plus descriptif, comme **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="604d8-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="604d8-130">Dans la page **Gestionnaires de connexions**, ajoutez ou créez le gestionnaire de connexions ODBC et attribuez-lui un nom descriptif, par exemple **MyODBCConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="604d8-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="604d8-131">Dans la page **script** , cliquez sur **modifier le script**, puis entrez le script ci-dessous dans la `ScriptMain` classe.</span><span class="sxs-lookup"><span data-stu-id="604d8-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="604d8-132">Fermez l’environnement de développement de script, fermez l’**Éditeur de transformation de script**, puis exécutez l’exemple.</span><span class="sxs-lookup"><span data-stu-id="604d8-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="604d8-133">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="604d8-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="604d8-134">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="604d8-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="604d8-135">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="604d8-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="604d8-136">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="604d8-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604d8-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="604d8-137">See Also</span></span>  
 [<span data-ttu-id="604d8-138">Création d’une destination à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="604d8-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  
