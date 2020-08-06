---
title: Éditeur de tâche de service Web (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.general.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 4d7df283-430d-4f0f-9dd4-5909554cd5eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dbacf2a2a867ab01039678ff4f43eebac839c11a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613523"
---
# <a name="web-service-task-editor-general-page"></a><span data-ttu-id="94703-102">Éditeur de tâche de service Web (page Général)</span><span class="sxs-lookup"><span data-stu-id="94703-102">Web Service Task Editor (General Page)</span></span>
  <span data-ttu-id="94703-103">Utilisez la page **Général** de la boîte de dialogue **Éditeur de tâche de service Web** pour définir un gestionnaire de connexions HTTP, spécifier l’emplacement du fichier WSDL (Web Services Description Language) qu’utilise la tâche de service web, décrire la tâche de service web et télécharger le fichier WSDL.</span><span class="sxs-lookup"><span data-stu-id="94703-103">Use the **General** page of the **Web Services Task Editor** dialog box to specify an HTTP connection manager, specify the location of the Web Services Description Language (WSDL) file the Web Service task uses, describe the Web Services task, and download the WSDL file.</span></span>  
  
 <span data-ttu-id="94703-104">Pour plus d’informations sur cette tâche, consultez [Tâche de service Web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="94703-104">For more information about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="94703-105">Options</span><span class="sxs-lookup"><span data-stu-id="94703-105">Options</span></span>  
 <span data-ttu-id="94703-106">**HTTPConnection**</span><span class="sxs-lookup"><span data-stu-id="94703-106">**HTTPConnection**</span></span>  
 <span data-ttu-id="94703-107">Sélectionnez un gestionnaire de connexions dans la liste ou cliquez sur \<**New connection...**> pour en créer un.</span><span class="sxs-lookup"><span data-stu-id="94703-107">Select a connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="94703-108">Le gestionnaire de connexions HTTP prend en charge uniquement l'authentification anonyme et l'authentification de base.</span><span class="sxs-lookup"><span data-stu-id="94703-108">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="94703-109">Il ne prend pas en charge l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="94703-109">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="94703-110">**Rubriques connexes :**  [Gestionnaire de connexions HTTP](connection-manager/http-connection-manager.md), [Éditeur du gestionnaire de connexions &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span><span class="sxs-lookup"><span data-stu-id="94703-110">**Related Topics:**  [HTTP Connection Manager](connection-manager/http-connection-manager.md), [HTTP Connection Manager Editor &#40;Server Page&#41;](../../2014/integration-services/http-connection-manager-editor-server-page.md)</span></span>  
  
 <span data-ttu-id="94703-111">**WSDLFile**</span><span class="sxs-lookup"><span data-stu-id="94703-111">**WSDLFile**</span></span>  
 <span data-ttu-id="94703-112">Tapez le chemin d’accès qualifié complet d’un fichier WSDL qui est en local sur l’ordinateur ou cliquez sur le bouton Parcourir **(...)** et recherchez ce fichier.</span><span class="sxs-lookup"><span data-stu-id="94703-112">Type the fully qualified path of a WSDL file that is local to the computer, or click the browse button **(...)** and locate this file.</span></span>  
  
 <span data-ttu-id="94703-113">Si vous avez déjà téléchargé manuellement le fichier WSDL sur l'ordinateur, sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="94703-113">If you have already manually downloaded the WSDL file to the computer, select this file.</span></span> <span data-ttu-id="94703-114">Toutefois, si le fichier WSDL n'a pas encore été téléchargé, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="94703-114">However, if the WSDL file has not yet been downloaded, follow these steps:</span></span>  
  
-   <span data-ttu-id="94703-115">Créez un fichier vide ayant l'extension de nom de fichier .wsdl.</span><span class="sxs-lookup"><span data-stu-id="94703-115">Create an empty file that has the ".wsdl" file name extension.</span></span>  
  
-   <span data-ttu-id="94703-116">Sélectionnez ce fichier vide pour l’option **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="94703-116">Select this empty file for the **WSDLFile** option.</span></span>  
  
-   <span data-ttu-id="94703-117">Affectez à **OverwriteWsdlFile** la valeur `True` pour permettre au fichier vide d’être remplacé par le fichier WSDL réel.</span><span class="sxs-lookup"><span data-stu-id="94703-117">Set the value of **OverwriteWSDLFile** to `True` to enable the empty file to be overwritten with the actual WSDL file.</span></span>  
  
-   <span data-ttu-id="94703-118">Cliquez sur **Télécharger WSDL** pour télécharger le fichier WSDL réel et remplacer le fichier vide.</span><span class="sxs-lookup"><span data-stu-id="94703-118">Click **Download WSDL** to download the actual WSDL file and overwrite the empty file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="94703-119">L’option **Télécharger WSDL** n’est pas activée tant que vous n’avez pas indiqué le nom d’un fichier local existant dans la zone **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="94703-119">The **Download WSDL** option is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
 <span data-ttu-id="94703-120">**OverwriteWSDLFile**</span><span class="sxs-lookup"><span data-stu-id="94703-120">**OverwriteWSDLFile**</span></span>  
 <span data-ttu-id="94703-121">Indiquez si le fichier WSDL de la tâche de service Web peut être remplacé.</span><span class="sxs-lookup"><span data-stu-id="94703-121">Indicate whether the WSDL file for the Web Service task can be overwritten.</span></span>  
  
 <span data-ttu-id="94703-122">Si vous envisagez de télécharger le fichier WSDL à l’aide du bouton **Télécharger WSDL** , définissez cette valeur sur `True` .</span><span class="sxs-lookup"><span data-stu-id="94703-122">If you intend to download the WSDL file by using the **Download WSDL** button, set this value to `True`.</span></span>  
  
 <span data-ttu-id="94703-123">**Nom**</span><span class="sxs-lookup"><span data-stu-id="94703-123">**Name**</span></span>  
 <span data-ttu-id="94703-124">Fournissez un nom unique pour la tâche de service Web.</span><span class="sxs-lookup"><span data-stu-id="94703-124">Provide a unique name for the Web Service task.</span></span> <span data-ttu-id="94703-125">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="94703-125">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94703-126">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="94703-126">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="94703-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="94703-127">**Description**</span></span>  
 <span data-ttu-id="94703-128">Entrez une description de la tâche de service Web.</span><span class="sxs-lookup"><span data-stu-id="94703-128">Type a description of the Web Service task.</span></span>  
  
 <span data-ttu-id="94703-129">**Télécharger WSDL**</span><span class="sxs-lookup"><span data-stu-id="94703-129">**Download WSDL**</span></span>  
 <span data-ttu-id="94703-130">Téléchargez le fichier WSDL.</span><span class="sxs-lookup"><span data-stu-id="94703-130">Download the WSDL file.</span></span>  
  
 <span data-ttu-id="94703-131">Ce bouton n’est pas activé tant que vous n’avez pas indiqué le nom d’un fichier local existant dans la zone **WSDLFile** .</span><span class="sxs-lookup"><span data-stu-id="94703-131">This button is not enabled until you provide the name of an existing local file in the **WSDLFile** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94703-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94703-132">See Also</span></span>  
 <span data-ttu-id="94703-133">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="94703-133">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="94703-134">[Éditeur de tâche de service Web &#40;page d’entrée&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span><span class="sxs-lookup"><span data-stu-id="94703-134">[Web Service Task Editor &#40;Input Page&#41;](../../2014/integration-services/web-service-task-editor-input-page.md) </span></span>  
 <span data-ttu-id="94703-135">[Éditeur de tâche de service Web &#40;page sortie&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="94703-135">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="94703-136">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="94703-136">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
