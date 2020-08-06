---
title: Ajout d’une mise en retrait | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611458"
---
# <a name="adding-indentation"></a><span data-ttu-id="0a574-102">Ajout d'une mise en retrait</span><span class="sxs-lookup"><span data-stu-id="0a574-102">Adding Indentation</span></span>
  <span data-ttu-id="0a574-103">L'Éditeur de requête vous permet de mettre en retrait de grandes sections de code en une seule étape et de modifier la longueur de mise en retrait.</span><span class="sxs-lookup"><span data-stu-id="0a574-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="0a574-104">Mise en retrait du code</span><span class="sxs-lookup"><span data-stu-id="0a574-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="0a574-105">Pour mettre en retrait plusieurs lignes de code</span><span class="sxs-lookup"><span data-stu-id="0a574-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="0a574-106">Dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0a574-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="0a574-107">Créez une deuxième requête qui sélectionne les colonnes **BusinessEntityID**, FirstName, **MiddleName**, et **LastName** dans la table **Person** du schéma **Person** .</span><span class="sxs-lookup"><span data-stu-id="0a574-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="0a574-108">Placez chaque colonne sur une ligne distincte afin que le code ressemble à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0a574-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="0a574-109">Sélectionnez tout le texte de `BusinessEntityID` à `LastName`.</span><span class="sxs-lookup"><span data-stu-id="0a574-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="0a574-110">Dans la barre d'outils **Éditeur SQL** , cliquez sur **Augmenter le retrait** pour mettre en retrait toutes les lignes en même temps.</span><span class="sxs-lookup"><span data-stu-id="0a574-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="0a574-111">Pour modifier la mise en retrait par défaut</span><span class="sxs-lookup"><span data-stu-id="0a574-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="0a574-112">Dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="0a574-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="0a574-113">Développez **Éditeur de texte**, développez **Tous les langages**, cliquez sur **Tabulations** et définissez les valeurs de mise en retrait qui conviennent.</span><span class="sxs-lookup"><span data-stu-id="0a574-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="0a574-114">Notez que vous pouvez modifier la valeur des mises en retrait ainsi que celle des tabulations. Vous pouvez également convertir ou non les tabulations en espaces.</span><span class="sxs-lookup"><span data-stu-id="0a574-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="0a574-115">![Apparence de la boîte de dialogue Onglets](media/tabsdialog.gif "Apparence de la boîte de dialogue Onglets")</span><span class="sxs-lookup"><span data-stu-id="0a574-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="0a574-116">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a574-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0a574-117">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="0a574-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0a574-118">Agrandissement de l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="0a574-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
