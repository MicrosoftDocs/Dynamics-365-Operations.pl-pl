---
title: "Używanie funkcji szybkiego importowania/eksportowania"
description: "Celem funkcji szybkiego importowania/eksportowania jest umożliwienie użytkownikom importowania i eksportowania przy użyciu mniejszej liczby kroków."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 4bb5bf73210abfc3fc06f7f291ae60fdf4298b71
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a><span data-ttu-id="8c5a9-103">Uruchamianie testowego narzędzia do przenoszenia danych (wersja beta) dla systemu Dynamics AX (AX 2012)</span><span class="sxs-lookup"><span data-stu-id="8c5a9-103">Run the Test Data Transfer Tool (beta) for Dynamics AX (AX 2012)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8c5a9-104">Celem funkcji szybkiego importowania/eksportowania jest umożliwienie użytkownikom importowania i eksportowania przy użyciu mniejszej liczby kroków.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-104">The purpose of Quick import export is to let you import and export with fewer steps.</span></span>

<span data-ttu-id="8c5a9-105">Dodaliśmy funkcję Szybkie importowanie/eksportowanie, aby umożliwić użytkownikom importowanie lub eksportowanie prostych zadań, które chcą szybko wykonać.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-105">We added the Quick Import Export feature to let users import or export simple jobs that they want to execute quickly.</span></span> <span data-ttu-id="8c5a9-106">W idealnej sytuacji ta funkcja jest używana w scenariuszach, w których plik jest automatycznie mapowany do systemu, a użytkownik nie musi przechodzić przez zaawansowane mapowanie ani tworzyć powtarzających się zadań importu lub eksportu.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-106">Ideally this feature is used in scenarios in which a file automatically maps to the system and user does not need to go through advanced mapping or create repeated import or export jobs.</span></span>

- <span data-ttu-id="8c5a9-107">Ta funkcja obsługuje pracę z jednostkami gotowymi (standardowymi) i niestandardowymi.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-107">This feature supports working with both out-of-the-box and custom entities.</span></span>
- <span data-ttu-id="8c5a9-108">Można importować z plików, a jeśli jest używane źródło danych ODBC, można wybrać zapytanie, które ma zostać użyte do zdefiniowania importu.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-108">You can import from files, and if you are using an ODBC data source, you can select a query to use to define your import.</span></span>
- <span data-ttu-id="8c5a9-109">Muszą być wcześniej zdefiniowane formaty danych źródłowych dla systemu AX lub pliku i trzeba wiedzieć, gdzie się one znajdują.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-109">You must have previously defined source data formats for either AX or File, and know where they are located.</span></span>
- <span data-ttu-id="8c5a9-110">Aby używać funkcji szybkiego importowania/eksportowania, nie trzeba tworzyć grupy przetwarzania. Zostanie ona utworzona automatycznie przez system podczas wykonywania zadania importu lub eksportu.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-110">You do not need to create a processing group to use quick import/export, one will be automatically created by the system when executing the import or export job.</span></span> <span data-ttu-id="8c5a9-111">Można także określić opcję przechowywania historii danych importowanych przez funkcję szybkiego importowania/eksportowania.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-111">You can also choose keep the history of the data imported by the quick import/export.</span></span>

  <span data-ttu-id="8c5a9-112">Należy zauważyć, że funkcja szybkiego importowania/eksportowania zakłada, że użytkownik jest obeznany z koncepcją struktury DIXF.</span><span class="sxs-lookup"><span data-stu-id="8c5a9-112">Note that Quick import export assumes that you are familiar with the concepts of DIXF.</span></span>




