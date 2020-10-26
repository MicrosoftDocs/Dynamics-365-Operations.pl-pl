---
title: Szablony serwisów
description: Można zdefiniować umowę serwisową jako szablon, tak aby później można było kopiować wiersze z tego szablonu do innej umowy serwisowej lub zlecenia serwisowego.
author: ShylaThompson
manager: tfehr
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8a92d67afe5fd427d1bc272c59e459cb1547d22
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983237"
---
# <a name="service-templates"></a><span data-ttu-id="c3b8d-103">Szablony serwisów</span><span class="sxs-lookup"><span data-stu-id="c3b8d-103">Service templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c3b8d-104">Można zdefiniować umowę serwisową jako szablon, tak aby później można było kopiować wiersze z tego szablonu do innej umowy serwisowej lub zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-104">You can define a service agreement as a template and copy the lines of the template later into another service agreement or into a service order.</span></span>

## <a name="example"></a><span data-ttu-id="c3b8d-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="c3b8d-105">Example</span></span>

<span data-ttu-id="c3b8d-106">Klient korzystający z usług danej firmy ma identyczne podnośniki serwisowe w pięciu różnych miejscach.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-106">A customer for whom you provide service has identical service elevators at five different locations.</span></span>

<span data-ttu-id="c3b8d-107">Trzeba skonfigurować pięć umów serwisowych dla tego klienta, po jednej dla każego miejsca.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-107">You want to set up five service agreements for the customer, one for each site.</span></span>
<span data-ttu-id="c3b8d-108">Aby zmniejszyć ilość pracy polegającej na powtarzaniu tych samych czynności i aby mieć pewność, że dane konfiguracyjne są identyczne we wszystkich umowach serwisowych, trzeba utworzyć umowę serwisową i zdefiniować ją jako szablon dla prac serwisowych związanych z podnośnikami.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-108">To limit repetitive setup work, and to make sure that the setup information in the service agreements is identical, you create a service agreement and specify it as a template for the service work on the elevators.</span></span>

<span data-ttu-id="c3b8d-109">Następnie można skopiować wiersze szablonu do pięciu nowych umów serwisowych, wypełniając je danymi z formularza.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-109">You can now copy the template lines into the five new service agreements, so that each service agreement is populated with the lines from the template.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="c3b8d-110">Utwórz szablon</span><span class="sxs-lookup"><span data-stu-id="c3b8d-110">Create a template</span></span>

<span data-ttu-id="c3b8d-111">Podczas tworzenia szablonu serwisu trzeba utworzyć umowę serwisową oraz wymagane wiersze w tej umowie, a następnie powiązać tę umowę z grupą szablonów serwisów.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-111">When you create a service template, you create a service agreement, create the required lines on it, and attach the service agreement to a service-template group.</span></span>

> [!NOTE]
> <span data-ttu-id="c3b8d-112">Umowa serwisowa może zostać zdefiniowana jako szablon tylko wtedy, gdy nie są z nią powiązane żadne zlecenia serwisowe.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-112">A service agreement can be defined as a template only if it has no service orders attached to it.</span></span> <span data-ttu-id="c3b8d-113">Z kolei nie można wygenerować zleceń serwisowych dla umowy serwisowej zdefiniowanej jako szablon.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-113">Also, no service orders can be generated from a service agreement that is defined as a template.</span></span>

## <a name="copy-template-lines"></a><span data-ttu-id="c3b8d-114">Kopiuj wiersze szablonu</span><span class="sxs-lookup"><span data-stu-id="c3b8d-114">Copy template lines</span></span>

<span data-ttu-id="c3b8d-115">Wiersze szablonu serwisu można skopiować do innej umowy serwisowej lub do zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-115">You can copy template lines from a service template into another service agreement or into a service order.</span></span>

<span data-ttu-id="c3b8d-116">Podczas kopiowania wierszy szablonu do zleceń serwisowych lub do umów serwisowych grupy szablonów są wyświetlane w postaci drzewa, w którym można rozwijać każdą grupę.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-116">When you copy template lines into your service orders or service agreements, your template groups are displayed in a tree view in which each group can be expanded.</span></span> <span data-ttu-id="c3b8d-117">W ten sposób moża wyświetlić każy szablon i wiersz szablonu.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-117">This display lets you view each template and template line.</span></span>

<span data-ttu-id="c3b8d-118">Łatwiej jest określić wiersze szablonu serwisu, które mają zostać skopiowane, gdy szablony zostaną pogrupowane przy użyciu nazw odzwierciedlających przeznaczenie szablonów.</span><span class="sxs-lookup"><span data-stu-id="c3b8d-118">It is easier to determine the service-template lines that you want to copy if you have grouped the templates under names that reflect the use of the templates.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3b8d-119">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="c3b8d-119">Related topics</span></span>

[<span data-ttu-id="c3b8d-120">Kopiowanie wierszy szablonów serwisu</span><span class="sxs-lookup"><span data-stu-id="c3b8d-120">Copy service templates lines</span></span>](copy-service-template-lines.md)
