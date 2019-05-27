---
title: Wgląd w płatności od odbiorców (wersja zapoznawcza)
description: W tym temacie opisano, jak narzędzie Wgląd w płatności od odbiorców może pomóc przewidzieć, kiedy faktura zostanie zapłacona, oraz pomaga organizacjom tworzyć strategie optymalizacji zwiększające prawdopodobieństwo otrzymania zapłaty w terminie.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566262"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="8b1dd-103">Wgląd w płatności od odbiorców (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="8b1dd-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="8b1dd-104">Ta funkcja stanowi część wydania kierowanego i jest dostępna tylko dla użytkowników, którzy zarejestrowali się na prywatną wersję zapoznawczą.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="8b1dd-105">Ta funkcja zostanie umieszczona w jednym z przyszłych wydań, które będzie ogólnie dostępne.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="8b1dd-106">Przegląd</span><span class="sxs-lookup"><span data-stu-id="8b1dd-106">Overview</span></span>

<span data-ttu-id="8b1dd-107">Organizacje często mają problemy z przewidzeniem, kiedy odbiorcy zapłacą faktury.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="8b1dd-108">Ten brak informacji może prowadzić do niedokładnych prognoz przepływów pieniężnych, nieefektywnych procesów windykacji oraz niebezpieczeństwa realizowania zamówień dla klientów, którzy stanowią ryzyko kredytowe.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="8b1dd-109">Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) wykorzystuje mechanizmy uczenia maszynowego do przewidywania, kiedy faktura zostanie zapłacona.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="8b1dd-110">Oferuje także strategie optymalizacji, które można dostosować w celu zmaksymalizowania prawdopodobieństwo terminowego otrzymania zapłaty od odbiorców.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="8b1dd-111">Prognozy</span><span class="sxs-lookup"><span data-stu-id="8b1dd-111">Predictions</span></span>

<span data-ttu-id="8b1dd-112">Mechanizm prognoz płatności umożliwia organizacjom usprawnienie procesów biznesowych przez:</span><span class="sxs-lookup"><span data-stu-id="8b1dd-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="8b1dd-113">Łatwe identyfikowanie faktur, po których można oczekiwać, że zostaną zapłacone z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="8b1dd-114">Podejmowanie właściwych działań w celu zwiększenia szans na otrzymanie zapłaty w terminie.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="8b1dd-115">Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) wykorzystuje mechanizmy uczenia maszynowego do przewidywania, kiedy faktura zostanie zapłacona.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="8b1dd-116">Narzędzie wykorzystuje historyczne dane faktur, płatności i odbiorców w celu zbudowania modelu uczenia maszynowego, który służy do przewidywania, kiedy faktura zostanie zapłacona.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="8b1dd-117">Dla każdej otwartej faktury narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) przewiduje trzy prawdopodobieństwa zapłaty:</span><span class="sxs-lookup"><span data-stu-id="8b1dd-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="8b1dd-118">Prawdopodobieństwo zapłaty na czas (w terminie wymagalności faktury).</span><span class="sxs-lookup"><span data-stu-id="8b1dd-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="8b1dd-119">Prawdopodobieństwo zapłaty w ciągu 30 dni od daty wymagalności faktury.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="8b1dd-120">Prawdopodobieństwo zapłaty po 30 dniach od daty wymagalności faktury.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="8b1dd-121">Prawdopodobieństwo zapłaty można oglądać w sekcji prognozowania.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="8b1dd-122">[![Prognozy płatności](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="8b1dd-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="8b1dd-123">Każdej fakturze jest również przypisywane największe prawdopodobieństwo zapłaty przy użyciu jednego z trzech zdefiniowanych powyżej scenariuszy przewidywanego prawdopodobieństwa zapłaty.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="8b1dd-124">Zwycięskim scenariuszem jest scenariusz o najwyższym prawdopodobieństwie zapłaty.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="8b1dd-125">Na przykład załóżmy, że dla faktury prognoza pokazuje 71-procentowe prawdopodobieństwo zapłaty na czas, 13-procentowe prawdopodobieństwo zapłaty w ciągu 30 dni od daty wymagalności oraz 16-procentowe prawdopodobieństwo zapłaty ponad 30 dni od daty wymagalności.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="8b1dd-126">Najwyższe prawdopodobieństwo pokazuje, że faktura znajdzie się w scenariuszu zapłaty na czas, dlatego zostanie oznaczona w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="8b1dd-127">[![Prognozy płatności](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="8b1dd-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="8b1dd-128">Strategie optymalizacji</span><span class="sxs-lookup"><span data-stu-id="8b1dd-128">Optimization strategies</span></span>

<span data-ttu-id="8b1dd-129">Oprócz prognoz płatności narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) może wykorzystywać strategie optymalizacji w celu zwiększenia szans na otrzymanie zapłaty w terminie.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="8b1dd-130">Pozwala to organizacji przeprowadzić analizę wariantową poprzez umożliwienie użytkownikom dostosowania parametrów faktur i odbiorców, a następnie porównanie powstałego wpływu na prawdopodobieństwo otrzymania płatności za faktury na czas.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="8b1dd-131">Na przykład organizacja może chcieć ocenić wpływ aktualizacji rabatu gotówkowego w fakturach na prawdopodobieństwo otrzymania płatności w terminie.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="8b1dd-132">Gdy faktury zostaną zoptymalizowane pod kątem używania nowego rabatu, użytkownicy mogą sprawdzić wpływ zastosowania rabatu na prawdopodobieństwo otrzymywania płatności za te faktury na czas.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="8b1dd-133">Jeśli koszt zastosowania rabatu jest minimalny w stosunku do korzyści polegającej na otrzymaniu płatności na czas, organizacja może postanowić stosować wybrany rabat do wszystkich przyszłych otwartych zamówień.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="8b1dd-134">Obecnie w narzędziu Wgląd w płatności od odbiorców (wersja zapoznawcza) jedną dostępną strategią optymalizacji są rabaty.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="8b1dd-135">[![Zoptymalizowane prognozy](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="8b1dd-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="8b1dd-136">Jak otrzymać aplikację Wgląd w płatności od odbiorców (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="8b1dd-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="8b1dd-137">Jeśli interesuje Cię wypróbowanie narzędzia Wgląd w płatności od odbiorców (wersja zapoznawcza), wyślij wiadomość e-mail do [zespołu odpowiedzialnego za wersje zapoznawcze funkcji wglądu w parametry finansowe](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8b1dd-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="8b1dd-138">Zasady zachowania poufności informacji</span><span class="sxs-lookup"><span data-stu-id="8b1dd-138">Privacy Statement</span></span>

<span data-ttu-id="8b1dd-139">Dane odbiorców w wersjach zapoznawczych narzędzi są przechowywane w Stanach Zjednoczonych.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="8b1dd-140">Ponadto wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 for Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="8b1dd-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>
