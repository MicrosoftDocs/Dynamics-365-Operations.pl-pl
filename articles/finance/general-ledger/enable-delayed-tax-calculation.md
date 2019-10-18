---
title: Włącz opóźnione obliczanie podatku w arkuszu
description: W tym temacie objaśniono sposób używania funkcji **Włącz opóźnione obliczanie podatku dla arkusza** w celu zwiększenia wydajności obliczania podatku, gdy objętość wierszy arkusza jest duża.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179367"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="0f25d-103">Włącz opóźnione obliczanie podatku w arkuszu</span><span class="sxs-lookup"><span data-stu-id="0f25d-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0f25d-104">W tym temacie objaśniono sposób używania funkcji **Włącz opóźnione obliczanie podatku dla arkusza** w celu zwiększenia wydajności obliczania podatku, gdy objętość wierszy arkusza jest duża.</span><span class="sxs-lookup"><span data-stu-id="0f25d-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="0f25d-105">Bieżące zachowanie przy obliczaniu podatku w arkuszu jest wyzwalane w czasie rzeczywistym, gdy użytkownik zaktualizuje pola związane z podatkiem, np. grupę podatków/grupę podatków dla towaru.</span><span class="sxs-lookup"><span data-stu-id="0f25d-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="0f25d-106">Każda aktualizacja na poziomie wiersza arkusza ponownie obliczy kwotę podatku we wszystkich wierszach arkusza.</span><span class="sxs-lookup"><span data-stu-id="0f25d-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="0f25d-107">Ułatwia użytkownikowi wyświetlanie obliczonej kwoty podatku w czasie rzeczywistym, ale może również spowodować, że powodować problemy wydajności jeśli liczba wierszy w arkuszu jest duża.</span><span class="sxs-lookup"><span data-stu-id="0f25d-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="0f25d-108">Ta funkcja stanowi opcję opóźnienia obliczania podatku w celu rozwiązania problemów z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="0f25d-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="0f25d-109">Jeśli ta funkcja jest włączona, kwota podatku będzie obliczana tylko wtedy, gdy użytkownik kliknie przycisk „podatek” lub zaksięguje arkusz.</span><span class="sxs-lookup"><span data-stu-id="0f25d-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="0f25d-110">Użytkownik może włączać/wyłączać parametr na trzech poziomach:</span><span class="sxs-lookup"><span data-stu-id="0f25d-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="0f25d-111">Według firmy</span><span class="sxs-lookup"><span data-stu-id="0f25d-111">By legal entity</span></span>
- <span data-ttu-id="0f25d-112">Nazwa arkusza</span><span class="sxs-lookup"><span data-stu-id="0f25d-112">By journal name</span></span>
- <span data-ttu-id="0f25d-113">Nagłówek arkusza</span><span class="sxs-lookup"><span data-stu-id="0f25d-113">By journal header</span></span>

<span data-ttu-id="0f25d-114">System przyjmie wartość parametru w nagłówku arkusza jako wersję ostateczną.</span><span class="sxs-lookup"><span data-stu-id="0f25d-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="0f25d-115">Wartość parametru w nagłówku arkusza będzie domyślnie określana na podstawie nazwy arkusza.</span><span class="sxs-lookup"><span data-stu-id="0f25d-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="0f25d-116">Podczas tworzenia nazwy arkusza wartość parametru w polu nazwa arkusza jest ustawiana domyślnie na podstawie wartości parametru księgi głównej</span><span class="sxs-lookup"><span data-stu-id="0f25d-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="0f25d-117">Wartości pól „rzeczywista kwota podatku” i „obliczona kwota podatku” w arkuszu zostaną ukryte, jeśli ten parametr jest włączony</span><span class="sxs-lookup"><span data-stu-id="0f25d-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="0f25d-118">Celem jest nie wprowadzać użytkownika w błąd, ponieważ wartość tych dwóch pól będzie zawsze wynosiła 0 przed rozpoczęciem obliczenia podatku przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0f25d-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="0f25d-119">Włącz opóźnione obliczanie podatku według firm</span><span class="sxs-lookup"><span data-stu-id="0f25d-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="0f25d-120">Wybierz kolejno opcje **Księga główna > Ustawienia księgi > Parametry księgi głównej**</span><span class="sxs-lookup"><span data-stu-id="0f25d-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="0f25d-121">Kliknij kartę **Podatek**.</span><span class="sxs-lookup"><span data-stu-id="0f25d-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="0f25d-122">Na skróconej karcie **Ogólne** znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz</span><span class="sxs-lookup"><span data-stu-id="0f25d-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="0f25d-123">Włącz opóźnione obliczanie podatku w arkuszu po nazwie arkusza</span><span class="sxs-lookup"><span data-stu-id="0f25d-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="0f25d-124">Wybierz kolejno opcje **Księga główna > Konfiguracja arkusza > Nazwy arkuszy**</span><span class="sxs-lookup"><span data-stu-id="0f25d-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="0f25d-125">Na skróconej karcie **Ogólne** znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz</span><span class="sxs-lookup"><span data-stu-id="0f25d-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="0f25d-126">Włącz opóźnione obliczanie podatku po arkuszu</span><span class="sxs-lookup"><span data-stu-id="0f25d-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="0f25d-127">Wybierz kolejno **Księga główna > Wpisy w arkuszu > Arkusze finansowe**.</span><span class="sxs-lookup"><span data-stu-id="0f25d-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="0f25d-128">Kliknij przycisk **Nowy**</span><span class="sxs-lookup"><span data-stu-id="0f25d-128">Click **New**</span></span>
3. <span data-ttu-id="0f25d-129">Wybierz nazwę arkusza</span><span class="sxs-lookup"><span data-stu-id="0f25d-129">Select a journal name</span></span>
4. <span data-ttu-id="0f25d-130">Kliknij przycisk **Ustawienia**</span><span class="sxs-lookup"><span data-stu-id="0f25d-130">Click **Setup**</span></span>
5. <span data-ttu-id="0f25d-131">Znajdź parametr **Obliczanie podatku opóźnionego**, włącz/wyłącz</span><span class="sxs-lookup"><span data-stu-id="0f25d-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
