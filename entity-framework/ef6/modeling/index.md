---
title: モデルの作成 - EF6
author: divega
ms.date: 2018-07-05
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 4890228E-CEA1-4595-B8AD-CA81253F8767
caps.latest.revision: 3
ms.openlocfilehash: e1eb4077a1fd77c66bb3e992e1d25a5de4fcc64c
ms.sourcegitcommit: 45494121254ad4fdcec613d1dd22d850068d6f39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2018
ms.locfileid: "37913513"
---
# <a name="creating-a-model"></a><span data-ttu-id="a89d9-102">モデルの作成</span><span class="sxs-lookup"><span data-stu-id="a89d9-102">Creating a Model</span></span>

<span data-ttu-id="a89d9-103">EF モデルは、アプリケーションのクラスとプロパティがデータベース テーブルと列にどのようにマップされるかに関する詳細を格納します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-103">An EF model stores the details about how application classes and properties map to database tables and columns.</span></span> <span data-ttu-id="a89d9-104">EF モデルは、主に次の 2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-104">There are two main ways to create an EF model:</span></span>

- <span data-ttu-id="a89d9-105">**Code First を使用する**: 開発者がコードを記述してモデルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-105">**Using Code First**: The developer writes code to specify the model.</span></span> <span data-ttu-id="a89d9-106">EF では、エンティティ クラスと開発者によって提供された追加のモデル構成に基づき、ランタイムにモデルとマッピングを生成します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-106">EF generates the models and mappings at runtime based on entity classes and additional model configuration provided by the developer.</span></span>

- <span data-ttu-id="a89d9-107">**EF Designer を使用する**: 開発者が EF Designer を使用してボックスと線を描画し、モデルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-107">**Using the EF Designer**: The developer draws boxes and lines to specify the model using the EF Designer.</span></span> <span data-ttu-id="a89d9-108">結果として得られるモデルは、EDMX 拡張子を持つファイルに XML として格納されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-108">The resulting model is stored as XML in a file with the EDMX extension.</span></span> <span data-ttu-id="a89d9-109">アプリケーションのドメイン オブジェクトは通常、概念モデルから自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-109">The application's domain objects are typically generated automatically from the conceptual model.</span></span>

## <a name="ef-workflows"></a><span data-ttu-id="a89d9-110">EF のワークフロー</span><span class="sxs-lookup"><span data-stu-id="a89d9-110">EF workflows</span></span>

<span data-ttu-id="a89d9-111">どちらの方法も、既存のデータベースを対象にしたり、新しいデータベースを作成したりするために使用できます。その結果、4 種類のワークフローが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-111">Both of these approaches can be used to target an existing database or create a new database, resulting in 4 different workflows.</span></span>
<span data-ttu-id="a89d9-112">最適な方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a89d9-112">Find out about which one is best for you:</span></span>  

|                                           | <span data-ttu-id="a89d9-113">コードを記述したい...</span><span class="sxs-lookup"><span data-stu-id="a89d9-113">I just want to write code...</span></span>                                                                                                                   | <span data-ttu-id="a89d9-114">デザイナーを使いたい...</span><span class="sxs-lookup"><span data-stu-id="a89d9-114">I want to use a designer...</span></span>                                                                                                                        |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a89d9-115">**新しいデータベースを作成している**</span><span class="sxs-lookup"><span data-stu-id="a89d9-115">**I am creating a new database**</span></span>          | [<span data-ttu-id="a89d9-116">**Code First** を使ってコードでモデルを定義してから、データベースを生成します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-116">Use **Code First** to define your model in code and then generate a database.</span></span>](~/ef6/modeling/code-first/workflows/new-database.md)           | [<span data-ttu-id="a89d9-117">**Model First** を使ってボックスと線でモデルを定義してから、データベースを生成します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-117">Use **Model First** to define your model using boxes and lines and then generate a database.</span></span>](~/ef6/modeling/designer/workflows/model-first.md)   |
| <span data-ttu-id="a89d9-118">**既存のデータベースにアクセスする必要がある**</span><span class="sxs-lookup"><span data-stu-id="a89d9-118">**I need to access an existing database**</span></span> | [<span data-ttu-id="a89d9-119">**Code First** を使って、既存のデータベースにマップするコードベースのモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-119">Use **Code First** to create a code based model that maps to an existing database.</span></span>](~/ef6/modeling/code-first/workflows/existing-database.md) | [<span data-ttu-id="a89d9-120">**Database First** を使って、既存のデータベースにマップする、ボックスと線のモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-120">Use **Database First** to create a boxes and lines model that maps to an existing database.</span></span>](~/ef6/modeling/designer/workflows/database-first.md) |

### <a name="watch-the-video-what-ef-workflow-should-i-use"></a><span data-ttu-id="a89d9-121">ビデオを見る: どのような EF のワークフローを使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a89d9-121">Watch the video: What EF workflow should I use?</span></span>

<span data-ttu-id="a89d9-122">この短いビデオでその違いと、最適なものを見つける方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-122">This short video explains the differences, and how to find the one that is right for you.</span></span>

<span data-ttu-id="a89d9-123">**提供**: [Rowan Miller](http://romiller.com/)</span><span class="sxs-lookup"><span data-stu-id="a89d9-123">**Presented By**: [Rowan Miller](http://romiller.com/)</span></span>

<span data-ttu-id="a89d9-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span><span class="sxs-lookup"><span data-stu-id="a89d9-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span></span>

<span data-ttu-id="a89d9-125">ビデオを見た後も EF Designer と Code First のどちらを使うべきか決められない場合は、どちらも学んでみましょう。</span><span class="sxs-lookup"><span data-stu-id="a89d9-125">If after watching the video you still don't feel comfortable deciding if you want to use the EF Designer or Code First, learn both!</span></span>

## <a name="a-look-under-the-hood"></a><span data-ttu-id="a89d9-126">内部的な処理</span><span class="sxs-lookup"><span data-stu-id="a89d9-126">A look under the hood</span></span>

<span data-ttu-id="a89d9-127">Code First と EF Designer のどちらを使っても、EF モデルには常に次のような複数のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a89d9-127">Regardless of whether you use Code First or the EF Designer, an EF model always has several components:</span></span>

- <span data-ttu-id="a89d9-128">アプリケーションのドメイン オブジェクト、またはエンティティ型自体。</span><span class="sxs-lookup"><span data-stu-id="a89d9-128">The application's domain objects or entity types themselves.</span></span> <span data-ttu-id="a89d9-129">これはしばしば、オブジェクト レイヤーと呼ばれます</span><span class="sxs-lookup"><span data-stu-id="a89d9-129">This is often referred to as the object layer</span></span>

- <span data-ttu-id="a89d9-130">[Entity Data Model](~/ef6/resources/glossary.md#entity-data-model) で説明される、ドメイン固有のエンティティ型とリレーションシップで構成される概念モデル。</span><span class="sxs-lookup"><span data-stu-id="a89d9-130">A conceptual model consisting of domain-specific entity types and relationships, described using the [Entity Data Model](~/ef6/resources/glossary.md#entity-data-model).</span></span> <span data-ttu-id="a89d9-131">このレイヤーはしばしば、文字 "C" (_概念_) で表されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-131">This layer is often referred to with the letter "C", for _conceptual_.</span></span>

- <span data-ttu-id="a89d9-132">データベースで定義されているテーブル、列およびリレーションシップを表すストレージ モデル。</span><span class="sxs-lookup"><span data-stu-id="a89d9-132">A storage model representing tables, columns and relationships as defined in the database.</span></span> <span data-ttu-id="a89d9-133">このレイヤーはしばしば、文字 "S" (_ストレージ_) で表されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-133">This layer is often referred to with the later "S", for _storage_.</span></span>  

- <span data-ttu-id="a89d9-134">概念モデルとデータベース スキーマ間のマッピング。</span><span class="sxs-lookup"><span data-stu-id="a89d9-134">A mapping between the conceptual model and the database schema.</span></span> <span data-ttu-id="a89d9-135">このマッピングはしばしば、"C-S" マッピングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-135">This mapping is often referred to as "C-S" mapping.</span></span>

<span data-ttu-id="a89d9-136">EF のマッピング エンジンは、"C-S" マッピングを利用してエンティティに対する作成、読み取り、更新、削除などの操作を、データベースのテーブルに対する同等の操作に変換します。</span><span class="sxs-lookup"><span data-stu-id="a89d9-136">EF's mapping engine leverages the "C-S" mapping to transform operations against entities - such as create, read, update, and delete - into equivalent operations against tables in the database.</span></span>

<span data-ttu-id="a89d9-137">概念モデルとアプリケーションのオブジェクト間のマッピングは、しばしば "O-C" マッピングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-137">The mapping between the conceptual model and the application's objects is often referred to as "O-C" mapping.</span></span> <span data-ttu-id="a89d9-138">"C-S" マップと比較すると、"O-C" のマッピングは暗黙的で、一対一です。.NET オブジェクトの図形と種類が一致するには、概念モデルに定義されたエンティティ、プロパティ、リレーションシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="a89d9-138">Compared to the "C-S" mapping, "O-C" mapping is implicit and one-to-one: entities, properties and relationships defined in the conceptual model are required to match the shapes and types of the .NET objects.</span></span> <span data-ttu-id="a89d9-139">EF4 以降は、EF 上での依存関係のないプロパティによる単純なオブジェクトで、オブジェクト レイヤーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-139">From EF4 and beyond, the objects layer can be composed of simple objects with properties without any dependencies on EF.</span></span> <span data-ttu-id="a89d9-140">これらは通常、Plain-Old CLR Objects (POCO) と呼ばれ、型とプロパティのマッピングは名前の照合規則に基づいて実行されます。</span><span class="sxs-lookup"><span data-stu-id="a89d9-140">These are usually referred to as Plain-Old CLR Objects (POCO) and mapping of types and properties is performed base on name matching conventions.</span></span> <span data-ttu-id="a89d9-141">以前、EF 3.5 では、"O-C" マッピングを実装するには、エンティティが EntityObject クラスから派生しないといけなかったり、EF 属性を運ばなければならないような、オブジェクト レイヤーの特定の制約がありました。</span><span class="sxs-lookup"><span data-stu-id="a89d9-141">Previously, in EF 3.5 there were specific restrictions for the object layer, like entities having to derive from the EntityObject class and having to carry EF attributes to implement the "O-C" mapping.</span></span>