---
title: 'Étape 4 : Ajout d’une destination de fichier plat | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f4088de3-16d8-419c-96a1-a2cd005d0a5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eff65f4a94a412d55af8055e302195f87ae4cdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704303"
---
# <a name="step-4-adding-a-flat-file-destination"></a><span data-ttu-id="557b3-102">Étape 4 : Ajout d’une destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="557b3-102">Step 4: Adding a Flat File Destination</span></span>
  <span data-ttu-id="557b3-103">La sortie d'erreur de la transformation Lookup Currency Key réachemine vers la transformation Script toutes les lignes de données ayant échoué au cours de l'opération de recherche.</span><span class="sxs-lookup"><span data-stu-id="557b3-103">The error output of the Lookup Currency Key transformation redirects to the Script transformation any data rows that failed the lookup operation.</span></span> <span data-ttu-id="557b3-104">Pour améliorer les informations recueillies sur les erreurs survenues, la transformation Script exécute un script chargé d'obtenir la description des erreurs.</span><span class="sxs-lookup"><span data-stu-id="557b3-104">To enhance information about the errors that occurred, the Script transformation runs a script that gets the description of errors.</span></span>  
  
 <span data-ttu-id="557b3-105">Au cours de cette tâche, vous allez enregistrer toutes ces informations sur les lignes échouées dans un fichier délimité pour les traiter ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="557b3-105">In this task, you will save all this information about the failed rows to a delimited file for later processing.</span></span> <span data-ttu-id="557b3-106">Pour enregistrer les lignes ayant échoué, vous devez ajouter et configurer un gestionnaire de connexions de fichiers plats pour le fichier texte censé contenir les données sur les erreurs, ainsi qu'une destination de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="557b3-106">To save the failed rows, you must add and configure a Flat File connection manager for the text file that will contain the error data and a Flat File destination.</span></span> <span data-ttu-id="557b3-107">En définissant les propriétés du gestionnaire de connexions de fichier plat utilisé par la destination de fichier plat, vous pouvez spécifier la façon dont elle met en forme et écrit le fichier texte.</span><span class="sxs-lookup"><span data-stu-id="557b3-107">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="557b3-108">Pour plus d’informations, consultez [Gestionnaire de connexions de fichiers plats](connection-manager/file-connection-manager.md) et [destination de fichier plat](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="557b3-108">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md) and [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
### <a name="to-add-and-configure-a-flat-file-destination"></a><span data-ttu-id="557b3-109">Pour ajouter et configurer une destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="557b3-109">To add and configure a Flat File destination</span></span>  
  
1.  <span data-ttu-id="557b3-110">Cliquez sur l'onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="557b3-110">Click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="557b3-111">Dans la **Boîte à outils SSIS**, développez **Autre**, puis faites glisser **Destination du fichier plat** sur l'aire de conception Flux de données.</span><span class="sxs-lookup"><span data-stu-id="557b3-111">In the **SSIS Toolbox**, expand **Other**, and drag **Flat File Destination** onto the data flow design surface.</span></span> <span data-ttu-id="557b3-112">Placez la **Destination de fichier plat** directement sous la transformation **Get Error Description** .</span><span class="sxs-lookup"><span data-stu-id="557b3-112">Put the **Flat File Destination** directly underneath the **Get Error Description** transformation.</span></span>  
  
3.  <span data-ttu-id="557b3-113">Cliquez sur la transformation **Obtenir la description de l’erreur** , puis faites glisser la flèche verte vers la nouvelle **Destination de fichier plat**.</span><span class="sxs-lookup"><span data-stu-id="557b3-113">Click the **Get Error Description** transformation, and then drag the green arrow onto the new **Flat File Destination**.</span></span>  
  
4.  <span data-ttu-id="557b3-114">Sur l'aire de conception **Flux de données** , cliquez sur **Destination de fichier plat** dans la transformation de **Destination de fichier plat** nouvellement ajoutée, puis remplacez le nom par **Failed Rows**.</span><span class="sxs-lookup"><span data-stu-id="557b3-114">On the **Data Flow** design surface, click **Flat File Destination** in the newly added **Flat File Destination** transformation, and change the name to **Failed Rows**.</span></span>  
  
5.  <span data-ttu-id="557b3-115">Cliquez avec le bouton droit sur la transformation **Failed Rows** , cliquez sur **Modifier**, puis dans **l’Éditeur de destination de fichier plat**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="557b3-115">Right-click the **Failed Rows** transformation, click **Edit**, and then in the **Flat File Destination Editor**, click **New**.</span></span>  
  
6.  <span data-ttu-id="557b3-116">Dans la boîte de dialogue **Format de fichier plat** , assurez-vous que **Délimité** est sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="557b3-116">In the **Flat File Format** dialog box, verify that **Delimited** is selected, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="557b3-117">Dans l **'éditeur du gestionnaire de connexions de fichiers plats**, dans la zone **nom du gestionnaire de connexions** , tapez `Error Data` .</span><span class="sxs-lookup"><span data-stu-id="557b3-117">In the **Flat File Connection Manager Editor**, in the **Connection Manager Name** box type `Error Data`.</span></span>  
  
8.  <span data-ttu-id="557b3-118">Dans la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** , cliquez sur **Parcourir**, puis recherchez le dossier dans lequel le fichier est à stocker.</span><span class="sxs-lookup"><span data-stu-id="557b3-118">In the **Flat File Connection Manager Editor** dialog box, click **Browse**, and locate the folder in which to store the file.</span></span>  
  
9. <span data-ttu-id="557b3-119">Dans la boîte de dialogue **ouvrir** , pour **nom de fichier**, tapez `ErrorOutput.txt` , puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="557b3-119">In the **Open** dialog box, for **File name**, type `ErrorOutput.txt`, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="557b3-120">Dans la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** , vérifiez que la zone **Paramètres régionaux** contient la valeur Anglais (États-Unis) et la zone **Page de codes** la valeur 1252 (ANSI - Latin I).</span><span class="sxs-lookup"><span data-stu-id="557b3-120">In the **Flat File Connection Manager Editor** dialog box, verify that the **Locale** box contains English (United States) and **Code page** contains 1252 (ANSI -Latin I).</span></span>  
  
11. <span data-ttu-id="557b3-121">Dans le volet Options, cliquez sur **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="557b3-121">In the options pane, click **Columns**.</span></span>  
  
     <span data-ttu-id="557b3-122">Notez qu'en plus des colonnes du fichier de données source, trois nouvelles colonnes sont présentes : ErrorCode, ErrorColumn et ErrorDescription.</span><span class="sxs-lookup"><span data-stu-id="557b3-122">Notice that, in addition to the columns from the source data file, three new columns are present: ErrorCode, ErrorColumn, and ErrorDescription.</span></span> <span data-ttu-id="557b3-123">Ces colonnes sont générées par la sortie d'erreur de la transformation Lookup Currency Key et par le script de la transformation Get Error Description. Vous pouvez les utiliser pour résoudre le problème à l'origine de l'échec de la ligne.</span><span class="sxs-lookup"><span data-stu-id="557b3-123">These columns are generated by the error output of the Lookup Currency Key transformation and by the script in the Get Error Description transformation, and can be used to troubleshoot the cause of the failed row.</span></span>  
  
12. <span data-ttu-id="557b3-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="557b3-124">Click **OK**.</span></span>  
  
13. <span data-ttu-id="557b3-125">Dans l' **Éditeur de destination de fichier plat**, désactivez la case à cocher **Remplacer les données du fichier** .</span><span class="sxs-lookup"><span data-stu-id="557b3-125">In the **Flat File Destination Editor**, clear the **Overwrite data in the file** check box.</span></span>  
  
     <span data-ttu-id="557b3-126">La désactivation de cette case à cocher conserve les erreurs sur plusieurs exécutions de packages.</span><span class="sxs-lookup"><span data-stu-id="557b3-126">Clearing this check box persists the errors over multiple package executions.</span></span>  
  
14. <span data-ttu-id="557b3-127">Dans l' **Éditeur de destination de fichier plat**, cliquez sur **Mappages** pour vérifier que toutes les colonnes sont correctes.</span><span class="sxs-lookup"><span data-stu-id="557b3-127">In the **Flat File Destination Editor**, click **Mappings** to verify that all the columns are correct.</span></span> <span data-ttu-id="557b3-128">Vous pouvez également renommer les colonnes dans la destination.</span><span class="sxs-lookup"><span data-stu-id="557b3-128">Optionally, you can rename the columns in the destination.</span></span>  
  
15. <span data-ttu-id="557b3-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="557b3-129">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="557b3-130">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="557b3-130">Next Steps</span></span>  
 [<span data-ttu-id="557b3-131">Étape 5 : Test du package du tutoriel de la leçon 4</span><span class="sxs-lookup"><span data-stu-id="557b3-131">Step 5: Testing the Lesson 4 Tutorial Package</span></span>](../integration-services/lesson-4-5-testing-the-lesson-4-tutorial-package.md)  
  
  
