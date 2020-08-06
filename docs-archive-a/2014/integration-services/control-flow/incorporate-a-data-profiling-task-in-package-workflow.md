---
title: Incorporer une tâche de profilage des données dans le flux de travail du package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling task [Integration Services], using output in workflow
ms.assetid: 39a51586-6977-4c45-b80b-0157a54ad510
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd3544586ac99f66b961f7961e4f4af4d9e4a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604079"
---
# <a name="incorporate-a-data-profiling-task-in-package-workflow"></a><span data-ttu-id="d78cd-102">Incorporer une tâche de profilage des données dans le flux de travail du package</span><span class="sxs-lookup"><span data-stu-id="d78cd-102">Incorporate a Data Profiling Task in Package Workflow</span></span>
  <span data-ttu-id="d78cd-103">Le profilage des données et le nettoyage des données ne sont pas des candidats pour un processus automatisé à leur stade initial.</span><span class="sxs-lookup"><span data-stu-id="d78cd-103">Data profiling and cleanup are not candidates for an automated process in their early stages.</span></span> <span data-ttu-id="d78cd-104">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], la sortie de la tâche de profilage des données doit habituellement faire l’objet d’une analyse visuelle et d’un jugement personnel pour qu’il soit déterminé si les violations signalées sont significatives ou excessives.</span><span class="sxs-lookup"><span data-stu-id="d78cd-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the output of the Data Profiling task usually requires visual analysis and human judgment to determine whether reported violations are meaningful or excessive.</span></span> <span data-ttu-id="d78cd-105">Même après avoir reconnu des problèmes de qualité des données, un plan soigneusement pensé doit être appliqué pour déterminer la meilleure approche pour le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="d78cd-105">Even after recognizing data quality problems, there still has to be a carefully thought-out plan that addresses the best approach for cleanup.</span></span>  
  
 <span data-ttu-id="d78cd-106">Toutefois, après avoir établi des critères de qualité des données, vous pouvez souhaiter automatiser une analyse et un nettoyage périodiques de la source de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-106">However, after criteria for data quality have been established, you might want to automate a periodic analysis and cleanup of the data source.</span></span> <span data-ttu-id="d78cd-107">Considérez les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="d78cd-107">Consider these scenarios:</span></span>  
  
-   <span data-ttu-id="d78cd-108">**Vérification de la qualité des données avant une charge incrémentielle**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-108">**Checking data quality before an incremental load**.</span></span> <span data-ttu-id="d78cd-109">Utilisez la tâche de profilage des données pour calculer le profil de ratio Null de la colonne de nouvelles données prévues pour la colonne CustomerName dans un tableau Customers.</span><span class="sxs-lookup"><span data-stu-id="d78cd-109">Use the Data Profiling task to compute the Column Null Ratio Profile of new data intended for the CustomerName column in a Customers table.</span></span> <span data-ttu-id="d78cd-110">Si le pourcentage de valeurs NULL est supérieur à 20 %, envoyez un message électronique qui contient la sortie de profil à l'opérateur et terminez le package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-110">If the percentage of null values is greater than 20%, send an e-mail message that contains the profile output to the operator and end the package.</span></span> <span data-ttu-id="d78cd-111">Dans le cas contraire, continuez la charge incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="d78cd-111">Otherwise, continue the incremental load.</span></span>  
  
-   <span data-ttu-id="d78cd-112">**Automatisation du nettoyage lorsque les conditions spécifiées sont satisfaites**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-112">**Automating cleanup when the specified conditions are met**.</span></span> <span data-ttu-id="d78cd-113">Utilisez la tâche de profilage des données pour calculer le profil d'inclusion de valeur de la colonne State (État) par rapport à une table de recherche d'états, et de la colonne ZIP Code/Postal Code (Code postal) par rapport à une table de recherche de codes postaux.</span><span class="sxs-lookup"><span data-stu-id="d78cd-113">Use the Data Profiling task to compute the Value Inclusion Profile of the State column against a lookup table of states, and of the ZIP Code/Postal Code column against a lookup table of zip codes.</span></span> <span data-ttu-id="d78cd-114">Si la puissance d'inclusion des valeurs d'état est inférieure à 80 %, mais que la puissance d'inclusion des valeurs de code postal est supérieure à 99 %, cela indique deux choses.</span><span class="sxs-lookup"><span data-stu-id="d78cd-114">If the inclusion strength of the state values is less than 80%, but the inclusion strength of the ZIP Code/Postal Code values is greater than 99%, this indicates two things.</span></span> <span data-ttu-id="d78cd-115">En premier lieu, les données d'état sont erronées.</span><span class="sxs-lookup"><span data-stu-id="d78cd-115">First, the state data is bad.</span></span> <span data-ttu-id="d78cd-116">En second lieu, les données de code postal sont correctes.</span><span class="sxs-lookup"><span data-stu-id="d78cd-116">Second, the ZIP Code/Postal Code data is good.</span></span> <span data-ttu-id="d78cd-117">Lancez une tâche de flux de données qui nettoie les données d'état en effectuant une recherche de la valeur d'état correcte à partir de la valeur de code postal actuelle.</span><span class="sxs-lookup"><span data-stu-id="d78cd-117">Launch a Data Flow task that cleans up the state data by performing a lookup of the correct state value from the current Zip Code/Postal Code value.</span></span>  
  
 <span data-ttu-id="d78cd-118">Une fois que vous avez un flux de travail dans lequel vous pouvez incorporer la tâche de flux de données, vous devez comprendre les étapes requises pour ajouter cette tâche.</span><span class="sxs-lookup"><span data-stu-id="d78cd-118">After you have a workflow into which you can incorporate the Data Flow task, you have to understand the steps that are required to add this task.</span></span> <span data-ttu-id="d78cd-119">La section suivante décrit le processus général d'incorporation de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-119">The next section describes the general process of incorporating the Data Flow task.</span></span> <span data-ttu-id="d78cd-120">Les deux sections finales décrivent comment connecter la tâche de flux de données, soit directement à une source de données, soit à des données transformées à partir du flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-120">The final two sections describe how to connect the Data Flow task either directly to a data source or to transformed data from the Data Flow.</span></span>  
  
## <a name="defining-a-general-workflow-for-the-data-flow-task"></a><span data-ttu-id="d78cd-121">Définition d'un flux de travail général pour la tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="d78cd-121">Defining a General Workflow for the Data Flow Task</span></span>  
 <span data-ttu-id="d78cd-122">La procédure décrite ci-dessous esquisse l'approche générale permettant d'utiliser la sortie de la tâche de profilage des données dans le flux de travail d'un package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-122">The following procedure outlines the general approach for using the output of the Data Profiling task in the workflow of a package.</span></span>  
  
#### <a name="to-use-the-output-of-the-data-profiling-task-programmatically-in-a-package"></a><span data-ttu-id="d78cd-123">Pour utiliser par programmation la sortie de la tâche de profilage des données dans un package</span><span class="sxs-lookup"><span data-stu-id="d78cd-123">To use the output of the Data Profiling task programmatically in a package</span></span>  
  
1.  <span data-ttu-id="d78cd-124">Ajoutez et configurez la tâche de profilage des données dans un package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-124">Add and configure the Data Profiling task in a package.</span></span>  
  
2.  <span data-ttu-id="d78cd-125">Configurez des variables de package qui contiendront les valeurs que vous souhaitez extraire des résultats du profil.</span><span class="sxs-lookup"><span data-stu-id="d78cd-125">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
3.  <span data-ttu-id="d78cd-126">Ajoutez et configurez une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-126">Add and configure a Script task.</span></span> <span data-ttu-id="d78cd-127">Connectez la tâche de script à la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-127">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="d78cd-128">Dans la tâche de script, écrivez un code pour lire les valeurs souhaitées dans le fichier de sortie de la tâche de profilage des données et remplir les variables de package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-128">In the Script task, write code that reads the desired values from the output file of the Data Profiling task and populates the package variables.</span></span>  
  
4.  <span data-ttu-id="d78cd-129">Dans les contraintes de précédence qui connectent la tâche de script aux branches situées en aval dans le flux de travail, écrivez des expressions qui utilisent les valeurs des variables pour diriger le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="d78cd-129">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
 <span data-ttu-id="d78cd-130">Lorsque vous incorporez la tâche de profilage des données dans le flux de travail d'un package, gardez à l'esprit les deux fonctionnalités suivantes de la tâche :</span><span class="sxs-lookup"><span data-stu-id="d78cd-130">When incorporating the Data Profiling task into the workflow of a package, keep these two features of the task in mind:</span></span>  
  
-   <span data-ttu-id="d78cd-131">**Sortie de la tâche**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-131">**Task output**.</span></span> <span data-ttu-id="d78cd-132">La tâche de profilage des données écrit sa sortie dans un fichier ou une variable de package au format XML selon le schéma DataProfile.xsd.</span><span class="sxs-lookup"><span data-stu-id="d78cd-132">The Data Profiling task writes its output to a file or a package variable in XML format according to the DataProfile.xsd schema.</span></span> <span data-ttu-id="d78cd-133">Par conséquent, vous devez interroger la sortie XML si vous souhaitez utiliser les résultats du profil dans le flux de travail conditionnel d'un package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-133">Therefore, you have to query the XML output if you want to use the profile results in the conditional workflow of a package.</span></span> <span data-ttu-id="d78cd-134">Vous pouvez facilement utiliser le langage de requête Xpath pour interroger cette sortie XML.</span><span class="sxs-lookup"><span data-stu-id="d78cd-134">You can easily use the Xpath query language to query this XML output.</span></span> <span data-ttu-id="d78cd-135">Pour étudier la structure de cette sortie XML, vous pouvez ouvrir un fichier de sortie exemple ou le schéma lui-même.</span><span class="sxs-lookup"><span data-stu-id="d78cd-135">To study the structure of this XML output, you can open a sample output file or the schema itself.</span></span> <span data-ttu-id="d78cd-136">Pour ouvrir le fichier de sortie ou le schéma, vous pouvez utiliser [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], un autre éditeur XML ou un éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="d78cd-136">To open the output file or schema, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], another XML editor, or a text editor, such as Notepad.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d78cd-137">Certains résultats du profil, affichés dans la visionneuse du profil des données, sont des valeurs calculées qui n'ont pas été trouvées directement dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="d78cd-137">Some of the profile results that are displayed in the Data Profile Viewer are calculated values that are not directly found in the output.</span></span> <span data-ttu-id="d78cd-138">Par exemple, la sortie du profil de ratio Null de la colonne contient le nombre total de lignes et le nombre de lignes qui contiennent des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="d78cd-138">For example, the output of the Column Null Ratio Profile contains the total number of rows and the number of rows that contain null values.</span></span> <span data-ttu-id="d78cd-139">Vous devez effectuer une requête sur ces deux valeurs, puis calculer le pourcentage des lignes qui contiennent des valeurs Null, pour obtenir le ratio Null de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d78cd-139">You have to query these two values, and then calculate the percentage of rows that contain null values, to obtain the column null ratio.</span></span>  
  
-   <span data-ttu-id="d78cd-140">**Entrée de la tâche**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-140">**Task input**.</span></span> <span data-ttu-id="d78cd-141">La tâche de profilage des données lit son entrée à partir des tables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d78cd-141">The Data Profiling task reads its input from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="d78cd-142">Par conséquent, vous devez enregistrer les données en mémoire dans des tables intermédiaires si vous voulez profiler les données qui ont déjà été chargées et transformées dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-142">Therefore, you have to save data that is in memory to staging tables if you want to profile data that has already been loaded and transformed in the data flow.</span></span>  
  
 <span data-ttu-id="d78cd-143">Les sections suivantes appliquent ce flux de travail général pour profiler les données qui proviennent directement d'une source de données externe ou qui proviennent transformées de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-143">The following sections apply this general workflow to profiling data that comes directly from an external data source or that comes transformed from the Data Flow task.</span></span> <span data-ttu-id="d78cd-144">Ces sections indiquent également comment gérer les conditions préalables d'entrée et de sortie de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-144">These sections also show how to handle the input and output requirements of the Data Flow task.</span></span>  
  
## <a name="connecting-the-data-profiling-task-directly-to-an-external-data-source"></a><span data-ttu-id="d78cd-145">Connexion de la tâche de profilage des données directement à une source de données externe</span><span class="sxs-lookup"><span data-stu-id="d78cd-145">Connecting the Data Profiling Task Directly to an External Data Source</span></span>  
 <span data-ttu-id="d78cd-146">La tâche de profilage des données peut profiler des données qui proviennent directement d'une source de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-146">The Data Profiling task can profile data that comes directly from a data source.</span></span>  <span data-ttu-id="d78cd-147">Pour illustrer cette fonction, l'exemple suivant utilise la tâche de profilage des données pour calculer un profil de ratio Null de colonne sur les colonnes de la table Person.Address dans la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d78cd-147">To illustrate this capability, the following example uses the Data Profiling task to compute a Column Null Ratio Profile on the columns of the Person.Address table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="d78cd-148">Ensuite, cet exemple utilise une tâche de script pour extraire les résultats du fichier de sortie et remplir les variables de package qui peuvent être utilisées pour diriger le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="d78cd-148">Then, this example uses a Script task to retrieve the results from the output file and populate package variables that can be used to direct workflow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78cd-149">La colonne AddressLine2 a été sélectionnée pour cet exemple simple, car elle contient un pourcentage élevé de valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="d78cd-149">The AddressLine2 column was selected for this simple example because this column contains a high percentage of null values.</span></span>  
  
 <span data-ttu-id="d78cd-150">Cet exemple inclut les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d78cd-150">This example consists of the following steps:</span></span>  
  
-   <span data-ttu-id="d78cd-151">Configuration des gestionnaires de connexions qui se connectent à la source de données externe et au fichier de sortie qui contiendra les résultats du profil.</span><span class="sxs-lookup"><span data-stu-id="d78cd-151">Configuring the connection managers that connect to the external data source and to the output file that will contain the profile results.</span></span>  
  
-   <span data-ttu-id="d78cd-152">Configuration des variables de package qui contiendront les valeurs requises par la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-152">Configuring the package variables that will hold the values needed by the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="d78cd-153">Configuration de la tâche de profilage des données permettant de calculer le profil de ratio Null de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d78cd-153">Configuring the Data Profiling task to compute the Column Null Ratio Profile.</span></span>  
  
-   <span data-ttu-id="d78cd-154">Configuration de la tâche de script qui utilisera la sortie XML de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-154">Configuring the Script task to work the XML output from the Data Profiling task.</span></span>  
  
-   <span data-ttu-id="d78cd-155">Configuration des contraintes de précédence qui contrôleront quelles branches situées en aval dans le flux de travail seront exécutées, en fonction des résultats de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-155">Configuring the precedence constraints that will control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
### <a name="configure-the-connection-managers"></a><span data-ttu-id="d78cd-156">Configurer les gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="d78cd-156">Configure the Connection Managers</span></span>  
 <span data-ttu-id="d78cd-157">Pour cet exemple, deux gestionnaires de connexions sont utilisés :</span><span class="sxs-lookup"><span data-stu-id="d78cd-157">For this example, there are two connection managers:</span></span>  
  
-   <span data-ttu-id="d78cd-158">Un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] qui se connecte à la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d78cd-158">An [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
-   <span data-ttu-id="d78cd-159">Un gestionnaire de connexions de fichiers qui crée le fichier de sortie qui contiendra les résultats de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-159">A File connection manager that creates the output file that will hold the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="d78cd-160">Pour configurer les gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="d78cd-160">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="d78cd-161">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], créez un nouveau package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d78cd-161">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="d78cd-162">Ajoutez un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] au package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-162">Add an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to the package.</span></span> <span data-ttu-id="d78cd-163">Configurez ce gestionnaire de connexions pour qu’il utilise le fournisseur de données .NET pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) et se connecte à une instance disponible de la base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d78cd-163">Configure this connection manager to use the NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) and to connect to an available instance of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span>  
  
     <span data-ttu-id="d78cd-164">Par défaut, le gestionnaire de connexions se nomme \<server name>.AdventureWorks1.</span><span class="sxs-lookup"><span data-stu-id="d78cd-164">By default, the connection manager has the following name: \<server name>.AdventureWorks1.</span></span>  
  
3.  <span data-ttu-id="d78cd-165">Ajoutez un gestionnaire de connexions de fichiers au package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-165">Add a File connection manager to the package.</span></span> <span data-ttu-id="d78cd-166">Configurez ce gestionnaire de connexions pour créer le fichier de sortie pour la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-166">Configure this connection manager to create the output file for the Data Profiling task.</span></span>  
  
     <span data-ttu-id="d78cd-167">Cet exemple utilise le nom de fichier, DataProfile1.xml.</span><span class="sxs-lookup"><span data-stu-id="d78cd-167">This example uses the file name, DataProfile1.xml.</span></span> <span data-ttu-id="d78cd-168">Par défaut, le gestionnaire de connexions a le même nom que le fichier.</span><span class="sxs-lookup"><span data-stu-id="d78cd-168">By default, the connection manager has the same name as the file.</span></span>  
  
### <a name="configure-the-package-variables"></a><span data-ttu-id="d78cd-169">Configurer les variables de package</span><span class="sxs-lookup"><span data-stu-id="d78cd-169">Configure the Package Variables</span></span>  
 <span data-ttu-id="d78cd-170">Cet exemple utilise deux variables de package :</span><span class="sxs-lookup"><span data-stu-id="d78cd-170">This example uses two package variables:</span></span>  
  
-   <span data-ttu-id="d78cd-171">La variable ProfileConnectionName transmet le nom du gestionnaire de connexions de fichiers à la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-171">The ProfileConnectionName variable passes the name of the File connection manager to the Script task.</span></span>  
  
-   <span data-ttu-id="d78cd-172">La variable AddressLine2NullRatio transmet au package le ratio de valeurs Null calculé pour cette colonne à partir de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-172">The AddressLine2NullRatio variable passes the calculated null ratio for this column out of the Script task to the package.</span></span>  
  
##### <a name="to-configure-the-package-variables-that-will-hold-profile-results"></a><span data-ttu-id="d78cd-173">Pour configurer les variables de package qui contiendront les résultats du profil</span><span class="sxs-lookup"><span data-stu-id="d78cd-173">To configure the package variables that will hold profile results</span></span>  
  
-   <span data-ttu-id="d78cd-174">Dans la fenêtre **Variables** , ajoutez et configurez les deux variables de package suivantes :</span><span class="sxs-lookup"><span data-stu-id="d78cd-174">In the **Variables** window, add and configure the following two package variables:</span></span>  
  
    -   <span data-ttu-id="d78cd-175">Entrez le nom, `ProfileConnectionName` , pour l’une des variables et définissez le type de cette variable sur **chaîne**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-175">Enter the name, `ProfileConnectionName`, for one of the variables and set the type of this variable to **String**.</span></span>  
  
    -   <span data-ttu-id="d78cd-176">Entrez le nom, `AddressLine2NullRatio` , pour l’autre variable et définissez le type de cette variable sur **double**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-176">Enter the name, `AddressLine2NullRatio`, for the other variable and set the type of this variable to **Double**.</span></span>  
  
### <a name="configure-the-data-profiling-task"></a><span data-ttu-id="d78cd-177">Configurer la tâche de profilage des données</span><span class="sxs-lookup"><span data-stu-id="d78cd-177">Configure the Data Profiling Task</span></span>  
 <span data-ttu-id="d78cd-178">La tâche de profilage des données doit être configurée de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="d78cd-178">The Data Profiling task has to be configured in the following way:</span></span>  
  
-   <span data-ttu-id="d78cd-179">Pour utiliser les données que le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] fournit comme entrée.</span><span class="sxs-lookup"><span data-stu-id="d78cd-179">To use the data that the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager supplies as input.</span></span>  
  
-   <span data-ttu-id="d78cd-180">Pour effectuer une opération de profil de ratio Null de la colonne sur les données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="d78cd-180">To perform a Column Null Ratio profile on the input data.</span></span>  
  
-   <span data-ttu-id="d78cd-181">Pour enregistrer les résultats du profil dans le fichier associé au gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d78cd-181">To save the profile results to the file that is associated with the File connection manager.</span></span>  
  
##### <a name="to-configure-the-data-profiling-task"></a><span data-ttu-id="d78cd-182">Pour configurer la tâche de profilage des données</span><span class="sxs-lookup"><span data-stu-id="d78cd-182">To configure the Data Profiling task</span></span>  
  
1.  <span data-ttu-id="d78cd-183">Ajoutez une tâche de profilage des données au flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="d78cd-183">To the Control Flow, add a Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="d78cd-184">Ouvrez l' **Éditeur de tâche de profilage de données** pour configurer la tâche.</span><span class="sxs-lookup"><span data-stu-id="d78cd-184">Open the **Data Profiling Task Editor** to configure the task.</span></span>  
  
3.  <span data-ttu-id="d78cd-185">Dans la page **Général** de l'éditeur, pour **Destination**, sélectionnez le nom du gestionnaire de connexions de fichiers que vous avez configuré précédemment.</span><span class="sxs-lookup"><span data-stu-id="d78cd-185">On the **General** page of the editor, for **Destination**, select the name of the File connection manager that you have previously configured.</span></span>  
  
4.  <span data-ttu-id="d78cd-186">Dans la page **Demandes de profil** de l'éditeur, créez un nouveau profil de ratio Null de la colonne.</span><span class="sxs-lookup"><span data-stu-id="d78cd-186">On the **Profile Requests** page of the editor, create a new Column Null Ratio Profile.</span></span>  
  
5.  <span data-ttu-id="d78cd-187">Dans le volet **Propriétés de la demande** , pour **ConnectionManager**, sélectionnez le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] que vous avez configuré précédemment.</span><span class="sxs-lookup"><span data-stu-id="d78cd-187">In the **Request properties** pane, for **ConnectionManager**, select the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that you have previously configured.</span></span> <span data-ttu-id="d78cd-188">Ensuite, pour **TableOrView**, sélectionnez Person.Address.</span><span class="sxs-lookup"><span data-stu-id="d78cd-188">Then, for **TableOrView**, select Person.Address.</span></span>  
  
6.  <span data-ttu-id="d78cd-189">Fermez l'Éditeur de tâche de profilage de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-189">Close the Data Profiling Task Editor.</span></span>  
  
### <a name="configure-the-script-task"></a><span data-ttu-id="d78cd-190">Configurer la tâche de script</span><span class="sxs-lookup"><span data-stu-id="d78cd-190">Configure the Script Task</span></span>  
 <span data-ttu-id="d78cd-191">La tâche de script doit être configurée pour extraire les résultats du fichier de sortie et remplir les variables de package configurées précédemment.</span><span class="sxs-lookup"><span data-stu-id="d78cd-191">The Script task has to be configured to retrieve the results from the output file and populate the package variables that were previously configured.</span></span>  
  
##### <a name="to-configure-the-script-task"></a><span data-ttu-id="d78cd-192">Pour configurer la tâche de script</span><span class="sxs-lookup"><span data-stu-id="d78cd-192">To configure the Script task</span></span>  
  
1.  <span data-ttu-id="d78cd-193">Ajoutez une tâche de script au flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="d78cd-193">To the Control Flow, add a Script task.</span></span>  
  
2.  <span data-ttu-id="d78cd-194">Connectez la tâche de script à la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-194">Connect the Script task to the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="d78cd-195">Ouvrez l' **éditeur de tâche de script** pour configurer la tâche.</span><span class="sxs-lookup"><span data-stu-id="d78cd-195">Open the **Script Task Editor** to configure the task.</span></span>  
  
4.  <span data-ttu-id="d78cd-196">Dans la page **Script** , sélectionnez votre langage de programmation préféré.</span><span class="sxs-lookup"><span data-stu-id="d78cd-196">On the **Script** page, select your preferred programming language.</span></span> <span data-ttu-id="d78cd-197">Ensuite, rendez les deux variables de package disponibles pour le script:</span><span class="sxs-lookup"><span data-stu-id="d78cd-197">Then, make the two package variables available to the script:</span></span>  
  
    1.  <span data-ttu-id="d78cd-198">Pour `ReadOnlyVariables` , sélectionnez `ProfileConnectionName` .</span><span class="sxs-lookup"><span data-stu-id="d78cd-198">For `ReadOnlyVariables`, select `ProfileConnectionName`.</span></span>  
  
    2.  <span data-ttu-id="d78cd-199">Pour **ReadWriteVariables**, sélectionnez `AddressLine2NullRatio` .</span><span class="sxs-lookup"><span data-stu-id="d78cd-199">For **ReadWriteVariables**, select `AddressLine2NullRatio`.</span></span>  
  
5.  <span data-ttu-id="d78cd-200">Sélectionnez **Modifier le script** pour ouvrir l'environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-200">Select **Edit Script** to open the script development environment.</span></span>  
  
6.  <span data-ttu-id="d78cd-201">Ajoutez une référence à l'espace de noms System.Xml.</span><span class="sxs-lookup"><span data-stu-id="d78cd-201">Add a reference to the System.Xml namespace.</span></span>  
  
7.  <span data-ttu-id="d78cd-202">Entrez l'exemple de code qui correspond à votre langage de programmation :</span><span class="sxs-lookup"><span data-stu-id="d78cd-202">Enter the sample code that corresponds to your programming language:</span></span>  
  
    ```vb  
    Imports System  
    Imports Microsoft.SqlServer.Dts.Runtime  
    Imports System.Xml  
  
    Public Class ScriptMain  
  
      Private FILENAME As String = "C:\ TEMP\DataProfile1.xml"  
      Private PROFILE_NAMESPACE_URI As String = "https://schemas.microsoft.com/DataDebugger/"  
      Private NULLCOUNT_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()"  
      Private TABLE_XPATH As String = _  
        "/default:DataProfile/default:DataProfileOutput/default:Profiles" & _  
        "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table"  
  
      Public Sub Main()  
  
        Dim profileConnectionName As String  
        Dim profilePath As String  
        Dim profileOutput As New XmlDocument  
        Dim profileNSM As XmlNamespaceManager  
        Dim nullCountNode As XmlNode  
        Dim nullCount As Integer  
        Dim tableNode As XmlNode  
        Dim rowCount As Integer  
        Dim nullRatio As Double  
  
        ' Open output file.  
        profileConnectionName = Dts.Variables("ProfileConnectionName").Value.ToString()  
        profilePath = Dts.Connections(profileConnectionName).ConnectionString  
        profileOutput.Load(profilePath)  
        profileNSM = New XmlNamespaceManager(profileOutput.NameTable)  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI)  
  
        ' Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM)  
        nullCount = CType(nullCountNode.Value, Integer)  
  
        ' Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM)  
        rowCount = CType(tableNode.Attributes("RowCount").Value, Integer)  
  
        ' Compute and return null ratio.  
        nullRatio = nullCount / rowCount  
        Dts.Variables("AddressLine2NullRatio").Value = nullRatio  
  
        Dts.TaskResult = Dts.Results.Success  
  
      End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SqlServer.Dts.Runtime;  
    using System.Xml;  
  
    public class ScriptMain  
    {  
  
      private string FILENAME = "C:\\ TEMP\\DataProfile1.xml";  
      private string PROFILE_NAMESPACE_URI = "https://schemas.microsoft.com/DataDebugger/";  
      private string NULLCOUNT_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:NullCount/text()";  
      private string TABLE_XPATH = "/default:DataProfile/default:DataProfileOutput/default:Profiles" + "/default:ColumnNullRatioProfile[default:Column[@Name='AddressLine2']]/default:Table";  
  
      public void Main()  
      {  
  
        string profileConnectionName;  
        string profilePath;  
        XmlDocument profileOutput = new XmlDocument();  
        XmlNamespaceManager profileNSM;  
        XmlNode nullCountNode;  
        int nullCount;  
        XmlNode tableNode;  
        int rowCount;  
        double nullRatio;  
  
        // Open output file.  
        profileConnectionName = Dts.Variables["ProfileConnectionName"].Value.ToString();  
        profilePath = Dts.Connections[profileConnectionName].ConnectionString;  
        profileOutput.Load(profilePath);  
        profileNSM = new XmlNamespaceManager(profileOutput.NameTable);  
        profileNSM.AddNamespace("default", PROFILE_NAMESPACE_URI);  
  
        // Get null count for column.  
        nullCountNode = profileOutput.SelectSingleNode(NULLCOUNT_XPATH, profileNSM);  
        nullCount = (int)nullCountNode.Value;  
  
        // Get row count for table.  
        tableNode = profileOutput.SelectSingleNode(TABLE_XPATH, profileNSM);  
        rowCount = (int)tableNode.Attributes["RowCount"].Value;  
  
        // Compute and return null ratio.  
        nullRatio = nullCount / rowCount;  
        Dts.Variables["AddressLine2NullRatio"].Value = nullRatio;  
  
        Dts.TaskResult = Dts.Results.Success;  
  
      }  
  
    }  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="d78cd-203">L'exemple de code indiqué dans cette procédure montre comment charger la sortie de la tâche de profilage des données à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="d78cd-203">The sample code shown in this procedure demonstrates how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="d78cd-204">Pour charger la sortie de la tâche de profilage des données à partir d'une variable de package, reportez-vous à l'exemple de code alternatif qui suit cette procédure.</span><span class="sxs-lookup"><span data-stu-id="d78cd-204">To load the output of the Data Profiling task from a package variable instead, see the alternative sample code that follows this procedure.</span></span>  
  
8.  <span data-ttu-id="d78cd-205">Fermez l'environnement de développement de script, puis l'éditeur de tâche de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-205">Close the script development environment, and then close the Script Task Editor.</span></span>  
  
#### <a name="alternative-code-reading-the-profile-output-from-a-variable"></a><span data-ttu-id="d78cd-206">Code alternatif - Lecture de la sortie du profil à partir d’une variable</span><span class="sxs-lookup"><span data-stu-id="d78cd-206">Alternative Code-Reading the Profile Output from a Variable</span></span>  
 <span data-ttu-id="d78cd-207">La procédure précédente montre comment charger la sortie de la tâche de profilage des données à partir d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="d78cd-207">The previous procedure shows how to load the output of the Data Profiling task from a file.</span></span> <span data-ttu-id="d78cd-208">Toutefois, une méthode alternative consiste à charger cette sortie à partir d'une variable de package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-208">However, an alternative method would be to load this output from a package variable.</span></span> <span data-ttu-id="d78cd-209">Pour charger la sortie à partir d'une variable, vous devez apporter les modifications suivantes dans l'exemple de code :</span><span class="sxs-lookup"><span data-stu-id="d78cd-209">To load the output from a variable, you have to make the following changes to the sample code:</span></span>  
  
-   <span data-ttu-id="d78cd-210">Appelez la méthode `LoadXml` de la classe `XmlDocument` à la place de la méthode `Load`.</span><span class="sxs-lookup"><span data-stu-id="d78cd-210">Call the `LoadXml` method of the `XmlDocument` class instead of the `Load` method.</span></span>  
  
-   <span data-ttu-id="d78cd-211">Dans l'éditeur de tâche de script, ajoutez le nom de la variable de package qui contient la sortie du profil dans la liste `ReadOnlyVariables` de la tâche.</span><span class="sxs-lookup"><span data-stu-id="d78cd-211">In the Script Task Editor, add the name of the package variable that contains the profile output to the task's `ReadOnlyVariables` list.</span></span>  
  
-   <span data-ttu-id="d78cd-212">Passez la valeur de chaîne de la variable à la méthode `LoadXML`, comme indiqué dans l'exemple de code suivant.</span><span class="sxs-lookup"><span data-stu-id="d78cd-212">Pass the string value of the variable to the `LoadXML` method, as shown in the following code example.</span></span> <span data-ttu-id="d78cd-213">(Cet exemple utilise "ProfileOutput" comme nom de la variable de package qui contient la sortie du profil.)</span><span class="sxs-lookup"><span data-stu-id="d78cd-213">(This example uses "ProfileOutput" as the name of the package variable that contains the profile output.)</span></span>  
  
    ```vb  
    Dim outputString As String  
    outputString = Dts.Variables("ProfileOutput").Value.ToString()  
    ...  
    profileOutput.LoadXml(outputString)  
    ```  
  
    ```csharp  
    string outputString;  
    outputString = Dts.Variables["ProfileOutput"].Value.ToString();  
    ...  
    profileOutput.LoadXml(outputString);  
    ```  
  
### <a name="configure-the-precedence-constraints"></a><span data-ttu-id="d78cd-214">Configurer les contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="d78cd-214">Configure the Precedence Constraints</span></span>  
 <span data-ttu-id="d78cd-215">Il convient de configurer les contraintes de précédence pour contrôler quelles branches situées en aval dans le flux de travail seront exécutées, en fonction des résultats de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-215">The precedence constraints have to be configured to control which downstream branches in the workflow are run based on the results of the Data Profiling task.</span></span>  
  
##### <a name="to-configure-the-precedence-constraints"></a><span data-ttu-id="d78cd-216">Pour configurer les contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="d78cd-216">To configure the precedence constraints</span></span>  
  
-   <span data-ttu-id="d78cd-217">Dans les contraintes de précédence qui connectent la tâche de script aux branches situées en aval dans le flux de travail, écrivez des expressions qui utilisent les valeurs des variables pour diriger le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="d78cd-217">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
     <span data-ttu-id="d78cd-218">Par exemple, vous pouvez définir l' **Opération d'évaluation** de la contrainte de précédence en spécifiant **Expression et contrainte**.</span><span class="sxs-lookup"><span data-stu-id="d78cd-218">For example, you might set the **Evaluation operation** of the precedence constraint to **Expression and Constraint**.</span></span> <span data-ttu-id="d78cd-219">Ensuite, vous pouvez utiliser `@AddressLine2NullRatio < .90` comme valeur de l'expression.</span><span class="sxs-lookup"><span data-stu-id="d78cd-219">Then, you might use `@AddressLine2NullRatio < .90` as the value of the expression.</span></span> <span data-ttu-id="d78cd-220">En conséquence, le flux de travail suit le chemin d'accès sélectionné lorsque les tâches précédentes réussissent et lorsque le pourcentage de valeurs NULL dans la colonne sélectionnée est inférieur à 90 %.</span><span class="sxs-lookup"><span data-stu-id="d78cd-220">This causes the workflow to follow the selected path when the previous tasks succeed, and when the percentage of null values in the selected column is less than 90%.</span></span>  
  
## <a name="connecting-the-data-profiling-task-to-transformed-data-from-the-data-flow"></a><span data-ttu-id="d78cd-221">Connexion de la tâche de profilage des données aux données transformées à partir du flux de données</span><span class="sxs-lookup"><span data-stu-id="d78cd-221">Connecting the Data Profiling Task to Transformed Data from the Data Flow</span></span>  
 <span data-ttu-id="d78cd-222">Au lieu de profiler directement des données à partir d'une source de données, vous pouvez profiler des données qui ont déjà été chargées et transformées dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-222">Instead of profiling data directly from a data source, you can profile data that has already been loaded and transformed in the data flow.</span></span> <span data-ttu-id="d78cd-223">Toutefois, la tâche de profilage des données fonctionne uniquement par rapport à des données persistantes et non pas par rapport à des données en mémoire.</span><span class="sxs-lookup"><span data-stu-id="d78cd-223">However, the Data Profiling task works only against persisted data, not against in-memory data.</span></span> <span data-ttu-id="d78cd-224">Par conséquent, vous devez en premier lieu utiliser un composant de destination pour enregistrer les données transformées dans une table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="d78cd-224">Therefore, you must first use a destination component to save the transformed data to a staging table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78cd-225">Lorsque vous configurez la tâche de profilage des données, vous devez sélectionner des tables et des colonnes existantes.</span><span class="sxs-lookup"><span data-stu-id="d78cd-225">When you configure the Data Profiling task, you have to select existing tables and columns.</span></span> <span data-ttu-id="d78cd-226">Par conséquent, vous devez créer la table intermédiaire au moment de la conception avant de pouvoir configurer la tâche.</span><span class="sxs-lookup"><span data-stu-id="d78cd-226">Therefore, you must create the staging table at design time before you can configure the task.</span></span> <span data-ttu-id="d78cd-227">En d'autres termes, ce scénario ne vous permet pas d'utiliser une table temporaire créée au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d78cd-227">In other words, this scenario does not allow you to use a temporary table that is created at run time.</span></span>  
  
 <span data-ttu-id="d78cd-228">Après avoir enregistré les données dans une table intermédiaire, vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d78cd-228">After saving the data to a staging table, you can do the following actions:</span></span>  
  
-   <span data-ttu-id="d78cd-229">utiliser la tâche de profilage des données pour profiler les données ;</span><span class="sxs-lookup"><span data-stu-id="d78cd-229">Use the Data Profiling task to profile the data.</span></span>  
  
-   <span data-ttu-id="d78cd-230">utiliser une tâche de script pour lire les résultats comme cela a été décrit précédemment dans cette rubrique ;</span><span class="sxs-lookup"><span data-stu-id="d78cd-230">Use a Script task to read the results as described earlier in this topic.</span></span>  
  
-   <span data-ttu-id="d78cd-231">utiliser ces résultats pour diriger le flux de travail suivant du package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-231">Use those results to direct the subsequent workflow of the package.</span></span>  
  
 <span data-ttu-id="d78cd-232">La procédure décrite ci-dessous fournit l'approche générale de l'utilisation de la tâche de profilage des données pour profiler des données qui ont été transformées par le flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-232">The following procedure provides the general approach for using the Data Profiling task to profile data that has been transformed by the data flow.</span></span> <span data-ttu-id="d78cd-233">Un grand nombre de ces étapes sont semblables à celles décrites précédemment pour le profilage de données qui proviennent directement d'une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="d78cd-233">Many of these steps are similar to the ones described earlier for profiling data that comes directly from an external data source.</span></span> <span data-ttu-id="d78cd-234">Vous pouvez réexaminer ces étapes précédentes pour obtenir plus d'informations sur la façon de configurer les différents composants.</span><span class="sxs-lookup"><span data-stu-id="d78cd-234">You might want to review those earlier steps for more information about how to configure the various components.</span></span>  
  
#### <a name="to-use-the-data-profiling-task-in-the-data-flow"></a><span data-ttu-id="d78cd-235">Pour utiliser la tâche de profilage des données dans le flux de données</span><span class="sxs-lookup"><span data-stu-id="d78cd-235">To use the Data Profiling task in the data flow</span></span>  
  
1.  <span data-ttu-id="d78cd-236">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], créez un package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-236">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create a package.</span></span>  
  
2.  <span data-ttu-id="d78cd-237">Dans le flux de données, ajoutez, configurez et connectez les sources et les transformations appropriées.</span><span class="sxs-lookup"><span data-stu-id="d78cd-237">In the Data Flow, add, configure, and connect the appropriate sources and transformations.</span></span>  
  
3.  <span data-ttu-id="d78cd-238">Dans le flux de données, ajoutez, configurez et connectez un composant de destination qui enregistre les données transformées dans une table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="d78cd-238">In the Data Flow, add, configure, and connect a destination component that saves the transformed data to a staging table.</span></span>  
  
4.  <span data-ttu-id="d78cd-239">Dans le flux de contrôle, ajoutez et configurez une tâche de profilage des données qui calcule les profils souhaités par rapport aux données transformées dans la table intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="d78cd-239">In the Control Flow, add and configure a Data Profiling task that computes the desired profiles against the transformed data in the staging table.</span></span> <span data-ttu-id="d78cd-240">Connectez la tâche de profilage des données à la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-240">Connect the Data Profiling task to the Data Flow task.</span></span>  
  
5.  <span data-ttu-id="d78cd-241">Configurez des variables de package qui contiendront les valeurs que vous souhaitez extraire des résultats du profil.</span><span class="sxs-lookup"><span data-stu-id="d78cd-241">Configure package variables to hold the values that you want to retrieve from the profile results.</span></span>  
  
6.  <span data-ttu-id="d78cd-242">Ajoutez et configurez une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="d78cd-242">Add and configure a Script task.</span></span> <span data-ttu-id="d78cd-243">Connectez la tâche de script à la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="d78cd-243">Connect the Script task to the Data Profiling task.</span></span> <span data-ttu-id="d78cd-244">Dans la tâche de script, écrivez un code pour lire les valeurs souhaitées dans la sortie de la tâche de profilage des données et remplir les variables de package.</span><span class="sxs-lookup"><span data-stu-id="d78cd-244">In the Script task, write code that reads the desired values from the output of the Data Profiling task and populates the package variables.</span></span>  
  
7.  <span data-ttu-id="d78cd-245">Dans les contraintes de précédence qui connectent la tâche de script aux branches situées en aval dans le flux de travail, écrivez des expressions qui utilisent les valeurs des variables pour diriger le flux de travail.</span><span class="sxs-lookup"><span data-stu-id="d78cd-245">In the precedence constraints that connect the Script task to downstream branches in the workflow, write expressions that use the values of the variables to direct the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78cd-246">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d78cd-246">See Also</span></span>  
 <span data-ttu-id="d78cd-247">[Configuration de la tâche de profilage des données](data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="d78cd-247">[Setup of the Data Profiling Task](data-profiling-task.md) </span></span>  
 [<span data-ttu-id="d78cd-248">Visionneuse du profil des données</span><span class="sxs-lookup"><span data-stu-id="d78cd-248">Data Profile Viewer</span></span>](data-profile-viewer.md)  
  
  
