---
title: Wgląd w płatności od odbiorców (wersja zapoznawcza)
description: W tym temacie opisano możliwości wglądu do płatności, które ułatwiają zrozumienie typowych praktyk płatności poszczególnych odbiorców i umożliwiają identyfikowanie okoliczności, które uzasadniają inicjowanie procesów zbierania danych wcześniej niż w przypadku wykonania innych czynności.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774026"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="eec8f-103">Wgląd w płatności od odbiorców (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="eec8f-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="eec8f-104">W tym temacie opisano możliwości wglądu do płatności, które ułatwiają zrozumienie typowych praktyk płatności poszczególnych odbiorców i umożliwiają identyfikowanie okoliczności, które uzasadniają inicjowanie procesów zbierania danych wcześniej niż w przypadku wykonania innych czynności.</span><span class="sxs-lookup"><span data-stu-id="eec8f-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="eec8f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="eec8f-105">Overview</span></span>

<span data-ttu-id="eec8f-106">Organizacje często mają problemy z przewidzeniem, kiedy odbiorcy zapłacą faktury.</span><span class="sxs-lookup"><span data-stu-id="eec8f-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="eec8f-107">Ten brakujący wgląd w nieścisły wpływ na mniej dokładne prognozy przepływów pieniężnych, procesy windykacji, które zaczynają zbyt późno, oraz zamówienia, które są zwalniane do odbiorców, którzy mogą domyślnie księgować.</span><span class="sxs-lookup"><span data-stu-id="eec8f-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="eec8f-108">Narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) organizacji może pomóc przewidzieć, kiedy faktura od odbiorcy zostanie zapłacona, oraz pomaga organizacjom tworzyć strategie kolekcji zwiększające prawdopodobieństwo otrzymania zapłaty w terminie.</span><span class="sxs-lookup"><span data-stu-id="eec8f-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="eec8f-109">Prognozy</span><span class="sxs-lookup"><span data-stu-id="eec8f-109">Predictions</span></span>

<span data-ttu-id="eec8f-110">Przewidywania płatności umożliwiają organizacjom ulepszanie procesów biznesowych dzięki łatwemu identyfikowaniu faktur, które prawdopodobnie zostaną spłacone, oraz podjęcia odpowiednich środków, które zwiększają szanse na zapłatę na czas.</span><span class="sxs-lookup"><span data-stu-id="eec8f-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="eec8f-111">Za pomocą modelu nauki maszyn, który wykorzystuje historyczne faktury, płatności i dane odbiorców, szczegółowe informacje o płatnościach (Podgląd) — dokładniejsze przewidywania w przypadku, gdy odbiorca zapłaci zaległą fakturę.</span><span class="sxs-lookup"><span data-stu-id="eec8f-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="eec8f-112">Dla każdej otwartej faktury narzędzie Wgląd w płatności od odbiorców (wersja zapoznawcza) przewiduje trzy prawdopodobieństwa zapłaty:</span><span class="sxs-lookup"><span data-stu-id="eec8f-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="eec8f-113">Prawdopodobieństwo dokonania płatności w czasie</span><span class="sxs-lookup"><span data-stu-id="eec8f-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="eec8f-114">Prawdopodobieństwo dokonania płatności opóźnionej</span><span class="sxs-lookup"><span data-stu-id="eec8f-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="eec8f-115">Prawdopodobieństwo dokonania płatności bardzo opóźnionej</span><span class="sxs-lookup"><span data-stu-id="eec8f-115">Probability of payment being made very late</span></span>

<span data-ttu-id="eec8f-116">Aby ułatwić organizacjom zrozumienie łącznej kwoty płatności, które mogą oczekiwać od odbiorcy w jednym z trzech przedziałów, na czas, późny i bardzo późno, informacje o płatnościach (wersja zapoznawcza) umożliwiają także Zagregowany widok oczekiwanych płatności.</span><span class="sxs-lookup"><span data-stu-id="eec8f-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="eec8f-117">[![Zagregowany widok prognoz płatności](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="eec8f-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="eec8f-118">Ponadto do każdej faktury jest przypisywane prawdopodobieństwo płatności na czas.</span><span class="sxs-lookup"><span data-stu-id="eec8f-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="eec8f-119">Jeśli prawdopodobieństwo płatności na czas jest mniejsze niż 50%, faktury są znakowane czerwoną kółkiem, aby wskazać, że te faktury mogą wymagać windykacji.</span><span class="sxs-lookup"><span data-stu-id="eec8f-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="eec8f-120">[![Prawdopodobieństwo listy płatności](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="eec8f-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="eec8f-121">Szczegóły płatności odbiorcy (wersja zapoznawcza) zawierają również informacje kontekstowe w celu wyjaśnienia przewidywania, takie jak najlepsze czynniki wpływające na prognozę, bieżący stan działalności gospodarczej z odbiorcą oraz szczegółowe informacje dotyczące historycznej płatności odbiorcy działa.</span><span class="sxs-lookup"><span data-stu-id="eec8f-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="eec8f-122">W wielu firmach proces windykacji był aktywnym działaniem; Proces windykacji nie rozpoczyna się do terminu wymagalności faktur.</span><span class="sxs-lookup"><span data-stu-id="eec8f-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="eec8f-123">Dzięki usłudze wgląd do płatności odbiorcy (wersja zapoznawcza) organizacje mogą być bardziej aktywne w sprawie windykacji.</span><span class="sxs-lookup"><span data-stu-id="eec8f-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="eec8f-124">Nie muszą oni już czekać na pozyskanie transakcji z powodu rozpoczęcia procesu zbierania danych.</span><span class="sxs-lookup"><span data-stu-id="eec8f-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="eec8f-125">Zamiast tego mogą one używać funkcji przewidywania płatności, aby określić, czy aktywne kolekcje będą poprawiać prawdopodobieństwo zapłaty na czas.</span><span class="sxs-lookup"><span data-stu-id="eec8f-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="eec8f-126">Funkcja przewidywania płatności zapewnia także firmom informacje potrzebne do potwierdzenia rozpoczęcia procesu zbierania danych w pierwszej kolejności.</span><span class="sxs-lookup"><span data-stu-id="eec8f-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="eec8f-127">Metodologia</span><span class="sxs-lookup"><span data-stu-id="eec8f-127">Methodology</span></span>

<span data-ttu-id="eec8f-128">Opracowywanie i wdrażanie rozwiązania AI jest trudne.</span><span class="sxs-lookup"><span data-stu-id="eec8f-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="eec8f-129">Pobiera zespół danych naukowców, ekspertów i inżynierów, którzy pracują przez dłuższy czas do formułowania, opracowywania, wdrażania i obsługiwania dostępnego rozwiązania AI.</span><span class="sxs-lookup"><span data-stu-id="eec8f-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="eec8f-130">Ułatwia to wdrażanie i korzystanie z rozwiązań AI w Finance.</span><span class="sxs-lookup"><span data-stu-id="eec8f-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="eec8f-131">Firma Microsoft udostępnia wstępnie używane rozwiązania AI w Finance, które są tworzone na podstawie modułu Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="eec8f-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="eec8f-132">Użytkownik końcowy z jednym kliknięciem przycisku może wdrożyć rozwiązanie AI i zacząć korzystanie z zalet inteligentnych prognoz.</span><span class="sxs-lookup"><span data-stu-id="eec8f-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="eec8f-133">Jeśli organizacja nie jest zadowolony z dokładnością prognoz, użytkownik zaawansowany za pomocą jednego kliknięcia może wejść w środowisko rozszerzenia AI Builder, a następnie zaznaczyć lub usunąć zaznaczenie pól używanych do generowania prognoz.</span><span class="sxs-lookup"><span data-stu-id="eec8f-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="eec8f-134">Jak są gotowe mogą one pociągać i publikować zmiany, a nowy model przeszkolony jest automatycznie pobierany na potrzeby prognoz w Finance.</span><span class="sxs-lookup"><span data-stu-id="eec8f-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="eec8f-135">Jak otrzymać aplikację Wgląd w płatności od odbiorców (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="eec8f-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="eec8f-136">Jeśli interesuje Cię wypróbowanie narzędzia [Wgląd w płatności od odbiorców (wersja zapoznawcza)](mailto:fiap@microsoft.com), wyślij wiadomość e-mail do zespołu odpowiedzialnego za wersje zapoznawcze funkcji wglądu w parametry finansowe.</span><span class="sxs-lookup"><span data-stu-id="eec8f-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="eec8f-137">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="eec8f-137">Privacy Notice</span></span>

<span data-ttu-id="eec8f-138">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="eec8f-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


