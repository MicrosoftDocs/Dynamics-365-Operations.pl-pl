---
title: Włączanie prognoz płatności odbiorcy (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009425"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="a5e7a-103">Włączanie prognoz płatności odbiorcy (wersja zapoznawcza)</span><span class="sxs-lookup"><span data-stu-id="a5e7a-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a5e7a-104">W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="a5e7a-105">Włączenie funkcji w obszarze roboczym **Zarządzanie funkcją** i wprowadzenie ustawień konfiguracji na stronie **Parametry Financial Insights**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="a5e7a-106">Ten temat zawiera również informacje, które mogą pomóc w skutecznym użyciu tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="a5e7a-107">Przed wykonaniem poniższych kroków należy się upewnić, że wstępne kroki zostały wykonane w temacie [Konfiguracja dla modułu Finance insights](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="a5e7a-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="a5e7a-108">Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="a5e7a-109">Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="a5e7a-110">(Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)</span><span class="sxs-lookup"><span data-stu-id="a5e7a-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="a5e7a-111">Jeśli wdrożenie systemu Microsoft Dynamics 365 Finance jest wdrożeniem Service Fabric, można pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="a5e7a-112">Zespół Finance Insights powinien już włączyć ten lot.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="a5e7a-113">Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="a5e7a-114">Włącz funkcję Wgląd w płatności od odbiorców:</span><span class="sxs-lookup"><span data-stu-id="a5e7a-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="a5e7a-115">Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="a5e7a-116">Znajdź funkcję o nazwie **Wgląd w płatności od odbiorców (wersja zapoznawcza)**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="a5e7a-117">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-117">Select **Enable now**.</span></span>

    <span data-ttu-id="a5e7a-118">Funkcja wglądu do płatności odbiorcy jest teraz włączona i gotowa do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="a5e7a-119">Skonfiguruj funkcję Wgląd w płatności od odbiorców:</span><span class="sxs-lookup"><span data-stu-id="a5e7a-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="a5e7a-120">Wybierz kolejno opcje **Kredyty i windykacji \> Ustawienia \> Finance Insights \> Parametry Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="a5e7a-121">[![Strona parametrów wglądów finansowych przed skonfigurowaniem funkcji](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="a5e7a-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="a5e7a-122">Na stronie **Parametry Financial insights** na karcie **Wgląd w płatności od odbiorców** wybierz łącze **Wyświetl pola danych używane w modelu prognozy**, aby otworzyć stronę **Pola danych modelu prognozy**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="a5e7a-123">Istnieje możliwość wyświetlenia domyślnej listy pól, które są używane do tworzenia modelu predykcyjnego sztucznej inteligencji (AI) prognoz płatności odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="a5e7a-124">Aby utworzyć model przewidywania za użyciu domyślnej listy pól, zamknij stronę **Pola danych dla modelu przewidywania**, a następnie na stronie **Parametry Financial Insights** ustaw wartość **Tak** opcji **Włącz funkcję**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="a5e7a-125">Umożliwia określenie okresu transakcji „bardzo późno” w celu zdefiniowania, jaki jest **bardzo późny** zasobnik przewidywania w firmie.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="a5e7a-126">Dla każdej otwartej faktury system prognozuje prawdopodobieństwo płatności w trzech przedziałach: **Na czas**, **Późno** i **Bardzo późno**.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="a5e7a-127">**Na czas** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty w terminie lub przed terminem płatności transakcji.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="a5e7a-128">**Opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po terminie płatności transakcji, ale przed rozpoczęciem okresu transakcji „bardzo późno”.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="a5e7a-129">**Bardzo opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po rozpoczęciu okresu transakcji „bardzo późno”.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a5e7a-130">W przypadku zmiany okresu transakcji „bardzo późno” i wybrania opcji **Zmień próg opóźnienia** po utworzeniu modelu przewidywania plików dla odbiorców, istniejący model przewidywania jest usuwany i tworzony jest nowy model.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="a5e7a-131">Nowy model przewidywania przeniesie transakcje do okresu „bardzo późno” na podstawie ustawień wprowadzonych w celu jego zdefiniowania.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="a5e7a-132">Po zdefiniowaniu okresu transakcji „bardzo późno” wybierz opcję **Utwórz model przewidywania**, aby utworzyć model przewidywania.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="a5e7a-133">Sekcja **model przewidywania** na stronie **parametry Financial Insights** zawiera stan modelu przewidywania.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a5e7a-134">W dowolnym momencie podczas tworzenia modelu przewidywania można wybrać opcję **Resetuj tworzenie modelu** w celu ponownego uruchomienia tego procesu.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="a5e7a-135">Funkcja została teraz skonfigurowana i jest gotowa do użycia.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="a5e7a-136">Po włączeniu i skonfigurowaniu funkcji oraz utworzeniu modelu przewidywania model przewidywania działa, sekcja **model przewidywania** na stronie **parametry Financial Insights** pokazuje dokładność modelu, tak jak to pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="a5e7a-137">[![Dokładność modelu przewidywania na stronie parametrów Financial insights](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="a5e7a-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="a5e7a-138">Szczegóły zwolnienia</span><span class="sxs-lookup"><span data-stu-id="a5e7a-138">Release details</span></span>

<span data-ttu-id="a5e7a-139">Publiczna wersja zapoznawcza Financial Insights jest dostępna dla wdrożeń próbnych w Stanach Zjednoczonych Ameryki, Europie i Zjednoczonym Królestwie.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="a5e7a-140">Firma Microsoft stopniowo zwiększa obsługę wielu regionów.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="a5e7a-141">Funkcje publicznej wersji zapoznawczej mogą być i powinny być włączone tylko w środowiskach piaskownicy warstwy 2.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="a5e7a-142">Nie można migrować ustawień i modeli AI utworzonych w środowisku piaskownicy do środowiska produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="a5e7a-143">Aby uzyskać więcej informacji, zobacz [Uzupełniające warunki użytkowania wersji zapoznawczych Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="a5e7a-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="a5e7a-144">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="a5e7a-144">Privacy notice</span></span>

<span data-ttu-id="a5e7a-145">Wersje zapoznawcze (1) mogą wykorzystywać mniej rygorystyczne funkcje ochrony prywatności i bezpieczeństwa niż usługa Dynamics 365 Finance and Operations, (2) nie są objęte umową dotyczącą poziomu usług (SLA) dla tej usługi, (3) nie powinny być używane do przetwarzania danych osobowych ani innych danych podlegających wymogom zapewnienia zgodności z przepisami lub regulacjami, oraz (4) mają ograniczone wsparcie techniczne.</span><span class="sxs-lookup"><span data-stu-id="a5e7a-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
