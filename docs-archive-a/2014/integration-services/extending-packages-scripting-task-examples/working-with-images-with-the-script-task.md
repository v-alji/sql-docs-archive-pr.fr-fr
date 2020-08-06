---
title: Utilisation d’images à l’aide de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- graphics [Integration Services]
- Script task [Integration Services], images
- Drawing namespace
- images [Integration Services]
- SSIS Script task, images
- Script task [Integration Services], examples
- thumbnails [Integration Services]
- System.Drawing namespace
- JPEG format [Integration Services]
- .jpeg files
ms.assetid: 74aeb7ab-51b2-4b9f-84ee-0b46a7908ab9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 75a5b72f87a4463d7270dc9f28529a81525860cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605655"
---
# <a name="working-with-images-with-the-script-task"></a><span data-ttu-id="588c7-102">Utilisation d'images à l'aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="588c7-102">Working with Images with the Script Task</span></span>
  <span data-ttu-id="588c7-103">Une base de données de produits ou d'utilisateurs contient généralement des images, en plus du texte et des données numériques.</span><span class="sxs-lookup"><span data-stu-id="588c7-103">A database of products or users frequently includes images in addition to text and numeric data.</span></span> <span data-ttu-id="588c7-104">L'espace de noms `System.Drawing` dans Microsoft .NET Framework fournit des classes permettant de manipuler des images.</span><span class="sxs-lookup"><span data-stu-id="588c7-104">The `System.Drawing` namespace in the Microsoft .NET Framework provides classes for manipulating images.</span></span>  
  
 [<span data-ttu-id="588c7-105">Exemple 1 : convertir des images au format JPEG</span><span class="sxs-lookup"><span data-stu-id="588c7-105">Example 1: Convert Images to JPEG Format</span></span>](#example1)  
  
 [<span data-ttu-id="588c7-106">Exemple 2 : créer et enregistrer des images miniatures</span><span class="sxs-lookup"><span data-stu-id="588c7-106">Example 2: Create and Save Thumbnail Images</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="588c7-107">Si vous souhaitez créer une tâche plus facilement réutilisable sur plusieurs packages, envisagez d'utiliser le code indiqué dans l'exemple de tâche de script comme point de départ d'une tâche personnalisée.</span><span class="sxs-lookup"><span data-stu-id="588c7-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="588c7-108">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="588c7-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="example-1-description-convert-images-to-jpeg-format"></a><a name="example1"></a> <span data-ttu-id="588c7-109">Description de l’exemple 1 : convertir des images au format JPEG</span><span class="sxs-lookup"><span data-stu-id="588c7-109">Example 1 Description: Convert Images to JPEG Format</span></span>  
 <span data-ttu-id="588c7-110">L'exemple suivant ouvre un fichier image spécifié par une variable et l'enregistre sous la forme d'un fichier JPEG compressé à l'aide d'un encodeur.</span><span class="sxs-lookup"><span data-stu-id="588c7-110">The following example opens an image file specified by a variable and saves it as a compressed JPEG file by using an encoder.</span></span> <span data-ttu-id="588c7-111">Le code pour extraire les informations de l'encodeur est encapsulé dans une fonction privée.</span><span class="sxs-lookup"><span data-stu-id="588c7-111">The code to retrieve encoder information is encapsulated in a private function.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="588c7-112">Pour configurer cet exemple de tâche de script destiné à un seul fichier image</span><span class="sxs-lookup"><span data-stu-id="588c7-112">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="588c7-113">Créez une variable chaîne appelée `CurrentImageFile` et attribuez lui la valeur du chemin d'accès et du nom d'un fichier image existant.</span><span class="sxs-lookup"><span data-stu-id="588c7-113">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="588c7-114">Dans la page **script** de l **'éditeur de tâche de script**, ajoutez la `CurrentImageFile` variable à la `ReadOnlyVariables` propriété.</span><span class="sxs-lookup"><span data-stu-id="588c7-114">On the **Script** page of the **Script Task Editor**, add the `CurrentImageFile` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="588c7-115">Dans le projet de script, définissez une référence à l'espace de noms `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="588c7-115">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
4.  <span data-ttu-id="588c7-116">Dans votre code, utilisez des instructions `Imports` pour importer les espaces de noms `System.Drawing` et `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="588c7-116">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="588c7-117">Pour configurer cet exemple de tâche de script destiné à plusieurs fichiers image</span><span class="sxs-lookup"><span data-stu-id="588c7-117">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="588c7-118">Placez la tâche de script dans un conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="588c7-118">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="588c7-119">Dans la page **Collection** de l’**Éditeur de boucle Foreach**, sélectionnez l’**énumérateur Foreach File**, puis spécifiez le chemin et le masque des fichiers sources, par exemple « \*.bmp ».</span><span class="sxs-lookup"><span data-stu-id="588c7-119">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the enumerator, and specify the path and file mask of the source files, such as "\*.bmp."</span></span>  
  
3.  <span data-ttu-id="588c7-120">Dans la page **Mappage de variables**, mappez la variable `CurrentImageFile` à l’index 0.</span><span class="sxs-lookup"><span data-stu-id="588c7-120">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="588c7-121">Cette variable transmet le nom du fichier en cours à la tâche de script à chaque itération de l'énumérateur.</span><span class="sxs-lookup"><span data-stu-id="588c7-121">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="588c7-122">Ces étapes s'ajoutent à celles répertoriées dans la procédure destinée à un seul fichier image.</span><span class="sxs-lookup"><span data-stu-id="588c7-122">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="588c7-123">Code de l’exemple 1</span><span class="sxs-lookup"><span data-stu-id="588c7-123">Example 1 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    'Create and initialize variables.  
    Dim currentFile As String  
    Dim newFile As String  
    Dim bmp As Bitmap  
    Dim eps As New Imaging.EncoderParameters(1)  
    Dim ici As Imaging.ImageCodecInfo  
    Dim supportedExtensions() As String = _  
        {".BMP", ".GIF", ".JPG", ".JPEG", ".EXIF", ".PNG", _  
        ".TIFF", ".TIF", ".ICO", ".ICON"}  
  
    Try  
        'Store the variable in a string for local manipulation.  
        currentFile = Dts.Variables("CurrentImageFile").Value.ToString  
        'Check the extension of the file against a list of  
        'files that the Bitmap class supports.  
        If Array.IndexOf(supportedExtensions, _  
            Path.GetExtension(currentFile).ToUpper) > -1 Then  
  
            'Load the file.  
            bmp = New Bitmap(currentFile)  
  
            'Calculate the new name for the compressed image.  
            'Note: This will overwrite existing JPEGs.  
            newFile = Path.Combine( _  
                Path.GetDirectoryName(currentFile), _  
                String.Concat(Path.GetFileNameWithoutExtension(currentFile), _  
                ".jpg"))  
  
            'Specify the compression ratio (0=worst quality, 100=best quality).  
            eps.Param(0) = New Imaging.EncoderParameter( _  
                Imaging.Encoder.Quality, 75)  
  
            'Retrieve the ImageCodecInfo associated with the jpeg format.  
            ici = GetEncoderInfo("image/jpeg")  
  
            'Save the file, compressing it into the jpeg encoding.  
            bmp.Save(newFile, ici, eps)  
        Else  
            'The file is not supported by the Bitmap class.  
            Dts.Events.FireWarning(0, "Image Resampling Sample", _  
                "File " & currentFile & " is not a supported format.", _  
                "", 0)  
         End If  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Image Resampling Sample", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Function GetEncoderInfo(ByVal mimeType As String) As Imaging.ImageCodecInfo  
  
    'The available image codecs are returned as an array,  
    'which requires code to iterate until the specified codec is found.  
  
    Dim count As Integer  
    Dim encoders() As Imaging.ImageCodecInfo  
  
    encoders = Imaging.ImageCodecInfo.GetImageEncoders()  
  
    For count = 0 To encoders.Length  
        If encoders(count).MimeType = mimeType Then  
            Return encoders(count)  
        End If  
    Next  
  
    'This point is only reached if a codec is not found.  
    Err.Raise(513, "Image Resampling Sample", String.Format( _  
        "The {0} codec is not available. Unable to compress file.", _  
            mimeType))  
    Return Nothing  
  
End Function  
  
```  
  
##  <a name="example-2-description-create-and-save-thumbnail-images"></a><a name="example2"></a> <span data-ttu-id="588c7-124">Description de l’exemple 2 : Créer et enregistrer des images miniatures</span><span class="sxs-lookup"><span data-stu-id="588c7-124">Example 2 Description: Create and Save Thumbnail Images</span></span>  
 <span data-ttu-id="588c7-125">L'exemple suivant ouvre un fichier image spécifié par une variable, crée une miniature de l'image en respectant les proportions et enregistre la miniature sous un nom de fichier modifié.</span><span class="sxs-lookup"><span data-stu-id="588c7-125">The following example opens an image file specified by a variable, creates a thumbnail of the image while maintaining a constant aspect ratio, and saves the thumbnail with a modified file name.</span></span> <span data-ttu-id="588c7-126">Le code qui calcule la hauteur et la largeur de la miniature en préservant les proportions est encapsulé dans une sous-routine privée.</span><span class="sxs-lookup"><span data-stu-id="588c7-126">The code that calculates the height and width of the thumbnail while maintaining a constant aspect ratio is encapsulated in a private subroutine.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-a-single-image-file"></a><span data-ttu-id="588c7-127">Pour configurer cet exemple de tâche de script destiné à un seul fichier image</span><span class="sxs-lookup"><span data-stu-id="588c7-127">To configure this Script Task example for use with a single image file</span></span>  
  
1.  <span data-ttu-id="588c7-128">Créez une variable chaîne appelée `CurrentImageFile` et attribuez lui la valeur du chemin d'accès et du nom d'un fichier image existant.</span><span class="sxs-lookup"><span data-stu-id="588c7-128">Create a string variable named `CurrentImageFile` and set its value to the path and file name of an existing image file.</span></span>  
  
2.  <span data-ttu-id="588c7-129">Créez également la variable de type entier `MaxThumbSize` et attribuez-lui une valeur en pixels, telle que 100.</span><span class="sxs-lookup"><span data-stu-id="588c7-129">Also create the `MaxThumbSize` integer variable and assign a value in pixels, such as 100.</span></span>  
  
3.  <span data-ttu-id="588c7-130">Dans la page **script** de l **'éditeur de tâche de script**, ajoutez les deux variables à la `ReadOnlyVariables` propriété.</span><span class="sxs-lookup"><span data-stu-id="588c7-130">On the **Script** page of the **Script Task Editor**, add both variables to the `ReadOnlyVariables` property.</span></span>  
  
4.  <span data-ttu-id="588c7-131">Dans le projet de script, définissez une référence à l'espace de noms `System.Drawing`.</span><span class="sxs-lookup"><span data-stu-id="588c7-131">In the script project, set a reference to the `System.Drawing` namespace.</span></span>  
  
5.  <span data-ttu-id="588c7-132">Dans votre code, utilisez des instructions `Imports` pour importer les espaces de noms `System.Drawing` et `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="588c7-132">In your code, use `Imports` statements to import the `System.Drawing` and `System.IO` namespaces.</span></span>  
  
#### <a name="to-configure-this-script-task-example-for-use-with-multiple-image-files"></a><span data-ttu-id="588c7-133">Pour configurer cet exemple de tâche de script destiné à plusieurs fichiers image</span><span class="sxs-lookup"><span data-stu-id="588c7-133">To configure this Script Task example for use with multiple image files</span></span>  
  
1.  <span data-ttu-id="588c7-134">Placez la tâche de script dans un conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="588c7-134">Place the Script task within a Foreach Loop container.</span></span>  
  
2.  <span data-ttu-id="588c7-135">Dans la page **Collection** de l’**Éditeur de boucle Foreach**, sélectionnez l’**énumérateur Foreach File** comme **Énumérateur**, puis spécifiez le chemin et le masque des fichiers sources, par exemple « \*.jpg ».</span><span class="sxs-lookup"><span data-stu-id="588c7-135">On the **Collection** page of the **Foreach Loop Editor**, select the **Foreach File Enumerator** as the **Enumerator**, and specify the path and file mask of the source files, such as "\*.jpg."</span></span>  
  
3.  <span data-ttu-id="588c7-136">Dans la page **Mappage de variables**, mappez la variable `CurrentImageFile` à l’index 0.</span><span class="sxs-lookup"><span data-stu-id="588c7-136">On the **Variable Mappings** page, map the `CurrentImageFile` variable to Index 0.</span></span> <span data-ttu-id="588c7-137">Cette variable transmet le nom du fichier en cours à la tâche de script à chaque itération de l'énumérateur.</span><span class="sxs-lookup"><span data-stu-id="588c7-137">This variable passes the current file name to the Script task on each iteration of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="588c7-138">Ces étapes s'ajoutent à celles répertoriées dans la procédure destinée à un seul fichier image.</span><span class="sxs-lookup"><span data-stu-id="588c7-138">These steps are in addition to the steps listed in the procedure for use with a single image file.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="588c7-139">Code de l’exemple 2</span><span class="sxs-lookup"><span data-stu-id="588c7-139">Example 2 Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim currentImageFile As String  
    Dim currentImage As Image  
    Dim maxThumbSize As Integer  
    Dim thumbnailImage As Image  
    Dim thumbnailFile As String  
    Dim thumbnailHeight As Integer  
    Dim thumbnailWidth As Integer  
  
    currentImageFile = Dts.Variables("CurrentImageFile").Value.ToString  
    thumbnailFile = Path.Combine( _  
        Path.GetDirectoryName(currentImageFile), _  
        String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), _  
        "_thumbnail.jpg"))  
  
    Try  
        currentImage = Image.FromFile(currentImageFile)  
  
        maxThumbSize = CType(Dts.Variables("MaxThumbSize").Value, Integer)  
        CalculateThumbnailSize( _  
            maxThumbSize, currentImage, thumbnailWidth, thumbnailHeight)  
  
        thumbnailImage = currentImage.GetThumbnailImage( _  
           thumbnailWidth, thumbnailHeight, Nothing, Nothing)  
        thumbnailImage.Save(thumbnailFile)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, "Script Task Example", _  
        ex.Message & ControlChars.CrLf & ex.StackTrace, _  
        String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
  
Private Sub CalculateThumbnailSize( _  
    ByVal maxSize As Integer, ByVal sourceImage As Image, _  
    ByRef thumbWidth As Integer, ByRef thumbHeight As Integer)  
  
    If sourceImage.Width > sourceImage.Height Then  
        thumbWidth = maxSize  
        thumbHeight = CInt((maxSize / sourceImage.Width) * sourceImage.Height)  
    Else  
        thumbHeight = maxSize  
        thumbWidth = CInt((maxSize / sourceImage.Height) * sourceImage.Width)  
    End If  
  
End Sub  
```  
  
```csharp  
bool ThumbnailCallback()  
        {  
            return false;  
        }  
        public void Main()  
        {  
  
            string currentImageFile;  
            Image currentImage;  
            int maxThumbSize;  
            Image thumbnailImage;  
            string thumbnailFile;  
            int thumbnailHeight = 0;  
            int thumbnailWidth = 0;  
  
            currentImageFile = Dts.Variables["CurrentImageFile"].Value.ToString();  
            thumbnailFile = Path.Combine(Path.GetDirectoryName(currentImageFile), String.Concat(Path.GetFileNameWithoutExtension(currentImageFile), "_thumbnail.jpg"));  
  
            try  
            {  
  
                currentImage = Image.FromFile(currentImageFile);  
  
                maxThumbSize = (int)Dts.Variables["MaxThumbSize"].Value;  
                CalculateThumbnailSize(maxThumbSize, currentImage, ref thumbnailWidth, ref thumbnailHeight);  
  
                Image.GetThumbnailImageAbort myCallback = new Image.GetThumbnailImageAbort(ThumbnailCallback);  
  
                thumbnailImage = currentImage.GetThumbnailImage(thumbnailWidth, thumbnailHeight, ThumbnailCallback, IntPtr.Zero);  
                thumbnailImage.Save(thumbnailFile);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
  
        private void CalculateThumbnailSize(int maxSize, Image sourceImage, ref int thumbWidth, ref int thumbHeight)  
        {  
  
            if (sourceImage.Width > sourceImage.Height)  
            {  
                thumbWidth = maxSize;  
                thumbHeight = (int)(sourceImage.Height * maxSize / sourceImage.Width);  
            }  
            else  
            {  
                thumbHeight = maxSize;  
                thumbWidth = (int)(sourceImage.Width * maxSize / sourceImage.Height);  
  
            }  
  
        }  
  
```  
  
<span data-ttu-id="588c7-140">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="588c7-140">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="588c7-141">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="588c7-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="588c7-142">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="588c7-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="588c7-143">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="588c7-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
