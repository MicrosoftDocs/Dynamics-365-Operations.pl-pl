---
title: Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych
description: W tym temacie wyjaśniono, jak można debugować źródła danych wykonanego formatu ER w celu lepszego zrozumienia skonfigurowanego przekształcenia i przepływu danych.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: bda81da80996d8cba38ac48e29c47ffef61d3bdb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562197"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="b3a6b-103">Debugowanie źródeł danych dla wykonanego formatu ER w celu analizowania przekształcenia i przepływu danych</span><span class="sxs-lookup"><span data-stu-id="b3a6b-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="b3a6b-104">Podczas [konfigurowania](tasks/er-format-configuration-2016-11.md) rozwiązania Raportowanie elektroniczne (ER) w celu generowania dokumentów wychodzących należy zdefiniować metody, które są używane do uzyskiwania danych z aplikacji i wprowadzania ich do generowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="b3a6b-105">Aby zapewnić wydajniejszą obsługę cyklu życia rozwiązania ER, powinno ono składać się z [modelu danych ER](general-electronic-reporting.md#DataModelComponent) i jego składników [mapowania](general-electronic-reporting.md#ModelMappingComponent), a także z [formatu ER](general-electronic-reporting.md#FormatComponentOutbound) i jego składników mapowania, dzięki czemu mapowanie modelu jest właściwe dla aplikacji, natomiast inne składniki pozostają niezależne od aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="b3a6b-106">Z tego powodu kilka składników rozwiązania ER może [wpłynąć na](general-electronic-reporting.md#FormatComponentOutbound) proces wprowadzania danych w wygenerowanych danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="b3a6b-107">Czasami dane wygenerowanego wyniku wyglądają inaczej niż te same dane w bazie danych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="b3a6b-108">W takich przypadkach określisz, który składnik ER jest odpowiedzialny za przekształcenie danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="b3a6b-109">Funkcja debugera źródła danych ER znacznie skraca czas i redukuje koszty związane z takim badaniem.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="b3a6b-110">Możesz przerwać wykonywanie formatu ER i otworzyć interfejs debugera źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="b3a6b-111">Można w nim przeglądać dostępne źródła danych i wybierać pojedyncze źródło danych do wykonania.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="b3a6b-112">Takie wykonanie ręczne symuluje wykonywanie źródła danych podczas rzeczywistego uruchamiania formatu ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="b3a6b-113">Wynik jest przedstawiany na stronie, na której można analizować odebrane dane.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="b3a6b-114">Aby włączyć funkcję debugowania źródła danych, w obszarze parametrów użytkownika rozwiązania ER ustaw opcję **Włącz debugowanie danych podczas uruchamiania formatu** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="b3a6b-115">Następnie możesz rozpocząć debugowanie źródła danych podczas uruchamiania formatu ER w celu wygenerowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="b3a6b-116">Możesz również użyć opcji **Rozpocznij debugowanie**, aby zainicjować debugowanie źródła danych dla formatu ER skonfigurowanego w [projektancie operacji ER](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="b3a6b-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="b3a6b-117">W tym temacie przedstawiono wytyczne dotyczące inicjowania debugowania źródła danych dla wykonywanych formatów ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="b3a6b-118">Wyjaśniono w nim, jak informacje mogą pomóc w zrozumieniu przepływu danych i przekształceń danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="b3a6b-119">Przykłady przedstawione w tym temacie używają procesu biznesowego do przetwarzania płatności dostawców.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="b3a6b-120">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="b3a6b-120">Limitations</span></span>

<span data-ttu-id="b3a6b-121">Debuger źródła danych może służyć do uzyskiwania dostępu do danych źródeł danych używanych w formatach ER uruchamianych w celu wygenerowania dokumentów wychodzących.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="b3a6b-122">Nie można używać go do debugowania źródeł danych w formatach ER zaprojektowanych z myślą o analizowaniu dokumentów przychodzących.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="b3a6b-123">Następujące ustawienia formatów ER nie są obecnie dostępne w przypadku debugowania źródła danych:</span><span class="sxs-lookup"><span data-stu-id="b3a6b-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="b3a6b-124">Przekształcenia formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-124">Format transformations</span></span>
- <span data-ttu-id="b3a6b-125">Reguły walidacji formatu i mapowania</span><span class="sxs-lookup"><span data-stu-id="b3a6b-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="b3a6b-126">Włączanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="b3a6b-126">Enabling expressions</span></span>
- <span data-ttu-id="b3a6b-127">Szczegóły zbierania danych w pamięci</span><span class="sxs-lookup"><span data-stu-id="b3a6b-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3a6b-128">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="b3a6b-128">Prerequisites</span></span>

- <span data-ttu-id="b3a6b-129">Aby wykonać przykłady opisane w tym temacie, trzeba mieć dostęp do jednej z następujących [ról](../sysadmin/tasks/assign-users-security-roles.md):</span><span class="sxs-lookup"><span data-stu-id="b3a6b-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="b3a6b-130">Deweloper raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b3a6b-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="b3a6b-131">Konsultant funkcjonalny raportowania elektronicznego</span><span class="sxs-lookup"><span data-stu-id="b3a6b-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="b3a6b-132">Administrator systemu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-132">System administrator</span></span>

- <span data-ttu-id="b3a6b-133">Firmę należy ustawić na wartość **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="b3a6b-134">Wykonaj kroki opisane w [dodatku 1](#appendix1) do tego tematu, aby pobrać składniki rozwiązania Microsoft ER wymagane do przetwarzania płatności dostawców.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="b3a6b-135">Wykonaj kroki opisane w [dodatku 2](#appendix2) do tego tematu, aby przygotować rozrachunki z dostawcami na potrzeby przetwarzania płatności dostawców przy użyciu pobranego rozwiązania ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="b3a6b-136">Przetwarzanie płatności dostawcy w celu pobrania pliku płatności</span><span class="sxs-lookup"><span data-stu-id="b3a6b-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="b3a6b-137">Wykonaj kroki opisane w [dodatku 3](#appendix3) do tego tematu, aby przetworzyć płatności dostawców.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Przetwarzanie płatności dostawcy w toku](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="b3a6b-139">Pobierz i zapisz plik ZIP na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="b3a6b-140">Wyodrębnij plik płatności **ISO20022 Credit transfer.xml** z pliku ZIP.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="b3a6b-141">Otwórz wyodrębniony plik płatności, korzystając z przeglądarki plików XML.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="b3a6b-142">W pliku płatności kod IBAN (International Bank Account Number) konta bankowego dostawcy nie zawiera spacji.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="b3a6b-143">W związku z tym różni się od wartości [wprowadzonej](#enteredIBANcode) na stronie **Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![Kod IBAN bez spacji](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="b3a6b-145">Możesz użyć debugera źródeł danych ER możesz sprawdzić, który składnik rozwiązania ER jest używany do obcinania spacji w kodzie IBAN.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="b3a6b-146">Włączanie debugowania źródła danych</span><span class="sxs-lookup"><span data-stu-id="b3a6b-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="b3a6b-147">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b3a6b-148">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="b3a6b-149">Ustaw opcję **Włącz debugowanie danych podczas uruchamiania formatu** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3a6b-150">Ten parametr jest właściwy dla użytkownika i właściwy dla firmy.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-150">This parameter is user-specific and company-specific.</span></span>

    ![Okno dialogowe parametry użytkownika](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="b3a6b-152">Przetwarzanie płatności dostawcy na potrzeby debugowania</span><span class="sxs-lookup"><span data-stu-id="b3a6b-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="b3a6b-153">Wykonaj kroki opisane w [dodatku 3](#appendix3) do tego tematu, aby przetworzyć płatności dostawców.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="b3a6b-154">W oknie komunikatu wybierz opcję **Tak**, aby potwierdzić, że chcesz przerwać przetwarzanie płatności dostawców i w zamian uruchomić debugowanie źródła danych na stronie **Debugowanie źródeł danych**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Okno komunikatu potwierdzającego](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="b3a6b-156">Debugowanie źródeł danych używanych podczas przetwarzania płatności</span><span class="sxs-lookup"><span data-stu-id="b3a6b-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="b3a6b-157">Debugowanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-157">Debug the model mapping</span></span>

1. <span data-ttu-id="b3a6b-158">Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Mapowanie modelu** w celu rozpoczęcia debugowania z tego składnika ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="b3a6b-159">W okienku źródła danych po lewej stronie wybierz źródło danych **\$notSentTransactions**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="b3a6b-160">Możesz wybrać pozycję **Odczytaj 1 rekord**, **Odczytaj 10 rekordów**, **Odczytaj 100 rekordów** lub **Odczytaj wszystkie rekordy**, aby wymusić odczytanie odpowiedniej liczby rekordów z wybranego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="b3a6b-161">W ten sposób można symulować dostęp do źródła danych z poziomu uruchomionego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="b3a6b-162">W okienku danych po prawej stronie wybierz opcję **Rozwiń wszystko**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="b3a6b-163">Zobaczysz, czy wybrane źródło danych typu **Lista rekordów** zawiera pojedynczy rekord.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="b3a6b-164">Rozwiń źródło danych **\$notSentTransactions** i wybierz zagnieżdżoną metodę **vendBankAccountInTransactionCompany()**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="b3a6b-165">Rozwiń metodę **vendBankAccountInTransactionCompany()** i wybierz zagnieżdżone pole **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="b3a6b-166">Wybierz pozycję **Pobierz wartość**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-166">Select **Get value**.</span></span>

    <span data-ttu-id="b3a6b-167">Możesz wybrać pozycję **Pobierz wartość**, aby wymusić odczytywanie wartości wybranego pola w wybranym źródle danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="b3a6b-168">W ten sposób można symulować dostęp do tego pola z poziomu uruchomionego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="b3a6b-169">Wybierz **Rozwiń wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-169">Select **Expand all**.</span></span>

    ![Wartość pola IBAN w mapowaniu modelu](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="b3a6b-171">Jak widzisz, mapowanie modelu nie odpowiada za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="b3a6b-172">Dlatego musisz kontynuować debugowanie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="b3a6b-173">Debugowanie mapowania formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-173">Debug the format mapping</span></span>

1. <span data-ttu-id="b3a6b-174">Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Mapowanie formatu** w celu kontynuowania debugowania z tego składnika ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="b3a6b-175">Wybierz źródło danych **\$PaymentByDebtor**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="b3a6b-176">Rozwiń pozycję **\$PaymentByDebtor**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="b3a6b-177">Rozwiń pozycję **\$PaymentByDebtor.Lines**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="b3a6b-178">Rozwiń pozycję **\$PaymentByDebtor.Lines.CreditorAccount**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="b3a6b-179">Rozwiń pozycję **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, a następnie wybierz pozycję **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="b3a6b-180">Wybierz pozycję **Pobierz wartość**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-180">Select **Get value**.</span></span>
8. <span data-ttu-id="b3a6b-181">Wybierz **Rozwiń wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-181">Select **Expand all**.</span></span>

    ![Wartość pola IBAN w mapowaniu formatu](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="b3a6b-183">Jak widzisz, źródła danych mapowania formatu nie odpowiadają za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="b3a6b-184">Dlatego musisz kontynuować debugowanie źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="b3a6b-185">Debugowanie formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-185">Debug the format</span></span>

1. <span data-ttu-id="b3a6b-186">Na stronie **Debugowanie źródeł danych** w okienku akcji wybierz pozycję **Format** w celu kontynuowania debugowania z tego składnika ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="b3a6b-187">Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="b3a6b-188">Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, a następnie wybierz pozycję **Odczytaj wszystkie rekordy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="b3a6b-189">Rozwiń elementy formatu, aby wybrać pozycję **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, a następnie wybierz pozycję **Pobierz wartość**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="b3a6b-190">Wybierz **Rozwiń wszystkie**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-190">Select **Expand all**.</span></span>

    ![Wartość pola IBAN w formacie](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="b3a6b-192">Jak widzisz, powiązanie formatu nie odpowiada za obcięte spacje, ponieważ zwrócony przez nie kod IBAN dla konta bankowego dostawcy zawiera spacje.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="b3a6b-193">Z tego względu element **BankIBAN** został skonfigurowany do używania przekształcenia formatu, które obcina spacje.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="b3a6b-194">Zamknij debuger źródła danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="b3a6b-195">Przeglądanie przekształceń formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-195">Review the format transformations</span></span>

1. <span data-ttu-id="b3a6b-196">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b3a6b-197">Na stronie **Konfiguracje** wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="b3a6b-198">Wybierz pozycję **Projektant**, a następnie rozwiń elementy w celu wybrania pozycji **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![Element BankIBAN na stronie Projektant formatów](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="b3a6b-200">Jak widzisz, element **BankIBAN** został skonfigurowany do używania przekształcenia **usuń niealfanumeryczne**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="b3a6b-201">Wybierz kartę **Przekształcenia**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-201">Select the **Transformations** tab.</span></span>

    ![Karta Przekształcenia dla elementu BankIBAN](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="b3a6b-203">Jak widzisz, przekształcenie typu **usuń niealfanumeryczne** zostało skonfigurowane do używania wyrażenia, które obcina spacje z podanego ciągu tekstowego.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="b3a6b-204">Rozpoczynanie debugowania w projektancie operacji</span><span class="sxs-lookup"><span data-stu-id="b3a6b-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="b3a6b-205">Podczas konfigurowania wersji roboczej formatu ER, który można uruchomić bezpośrednio z poziomu projektanta operacji, można uzyskać dostęp do debugera źródła danych, wybierając pozycję **Rozpocznij debugowanie** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Przycisk Rozpocznij debugowanie na stronie Projektant formatów](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="b3a6b-207">Do debugowania jest dostępne mapowanie formatu oraz składniki formatu dla edytowanego formatu ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="b3a6b-208">Rozpoczynanie debugowania w projektancie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="b3a6b-209">Podczas konfigurowania mapowania modelu ER, który można uruchomić bezpośrednio ze strony **Mapowanie modelu**, można uzyskać dostęp do debugera źródła danych, wybierając pozycję **Rozpocznij debugowanie** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Przycisk Rozpocznij debugowanie na stronie projektanta mapowania modelu](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="b3a6b-211">Do debugowania jest dostępny składnik mapowania modelu dla edytowanego mapowania ER.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="b3a6b-212">Dodatek 1: pobieranie rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="b3a6b-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="b3a6b-213">Pobieranie rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="b3a6b-213">Download an ER solution</span></span>

<span data-ttu-id="b3a6b-214">Jeśli chcesz użyć rozwiązania ER do wygenerowania pliku płatności elektronicznych dla przetwarzanej płatności dostawcy, możesz [pobrać](download-electronic-reporting-configuration-lcs.md) format płatności ER **Polecenie przelewu ISO20022**, który jest dostępny z biblioteki aktywów wspólnych w usługach Microsoft Dynamics Lifecycle Services (LCS) lub z repozytorium globalnego.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Importowanie formatu płatności ER na stronie Repozytorium konfiguracji](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="b3a6b-216">Oprócz wybranego formatu ER następujące [konfiguracje](general-electronic-reporting.md#Configuration) muszą zostać automatycznie zaimportowane do wystąpienia usługi Microsoft Dynamics 365 Finance jako część rozwiązania ER **Polecenie przelewu ISO20022**:</span><span class="sxs-lookup"><span data-stu-id="b3a6b-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="b3a6b-217">[Konfiguracja modelu danych ER](general-electronic-reporting.md#DataModelComponent) **Model płatności**</span><span class="sxs-lookup"><span data-stu-id="b3a6b-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="b3a6b-218">[Konfiguracja formatu ER](general-electronic-reporting.md#FormatComponentOutbound) **Polecenie przelewu ISO20022**</span><span class="sxs-lookup"><span data-stu-id="b3a6b-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="b3a6b-219">[Konfiguracja mapowania modelu ER](general-electronic-reporting.md#ModelMappingComponent) **Mapowanie 1611 modelu płatności**</span><span class="sxs-lookup"><span data-stu-id="b3a6b-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="b3a6b-220">Konfiguracja mapowania modelu ER **Mapowanie modelu płatności do miejsca docelowego ISO20022**</span><span class="sxs-lookup"><span data-stu-id="b3a6b-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="b3a6b-221">Te konfiguracje można znaleźć na stronie **Konfiguracje** struktury ER (**Administracja organizacją** \> **Raportowanie elektroniczne** \> **Konfiguracje**).</span><span class="sxs-lookup"><span data-stu-id="b3a6b-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![Zaimportowane konfiguracje na stronie Konfiguracje](./media/er-data-debugger-configurations.png)

<span data-ttu-id="b3a6b-223">Jeśli w drzewie konfiguracji brakuje dowolnej z wymienionych wcześniej konfiguracji, należy pobrać ją ręcznie z biblioteki aktywów wspólnych usług LCS w taki sam sposób, w jaki pobrano format płatności ER **Polecenie przelewu ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="b3a6b-224">Analizowanie pobranego rozwiązania ER</span><span class="sxs-lookup"><span data-stu-id="b3a6b-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="b3a6b-225">Przeglądanie mapowania modelu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-225">Review the model mapping</span></span>

1. <span data-ttu-id="b3a6b-226">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b3a6b-227">Wybierz pozycję **Model płatności** \> **Mapowanie 1611 modelu płatności**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="b3a6b-228">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-228">Select **Designer**.</span></span>
4. <span data-ttu-id="b3a6b-229">Wybierz rekord mapowania **Mapowanie modelu płatności ISO20022 CT**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="b3a6b-230">Wybierz pozycję **Projektant**, a następnie przejrzyj otwarte mapowanie modelu.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="b3a6b-231">Zauważ, że pole **Płatności** modelu danych jest powiązane ze źródłem danych **\$notSentTransactions**, które zwraca listę przetwarzanych wierszy płatności dostawcy.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Pole Płatności na stronie projektanta mapowania modelu](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="b3a6b-233">Przeglądanie mapowania formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-233">Review the format mapping</span></span>

1. <span data-ttu-id="b3a6b-234">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b3a6b-235">Wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="b3a6b-236">Wybierz opcję **Konstruktor**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-236">Select **Designer**.</span></span>
4. <span data-ttu-id="b3a6b-237">Na karcie **Mapowanie** przejrzyj otwarte mapowanie formatu.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="b3a6b-238">Zwróć uwagę, że element **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** pliku **ISO20022CTReports** \> **XMLHeader** jest powiązany ze źródłem danych **\$PaymentByDebtor**, które skonfigurowano do grupowania rekordów pola **Płatności** modelu danych.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![Element PmtInf na stronie Projektant formatów](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="b3a6b-240">Przeglądanie formatu</span><span class="sxs-lookup"><span data-stu-id="b3a6b-240">Review the format</span></span>

1. <span data-ttu-id="b3a6b-241">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="b3a6b-242">Wybierz pozycję **Model płatności** \> **Polecenie przelewu ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="b3a6b-243">Wybierz pozycję **Projektant**, a następnie przejrzyj otwarty format.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="b3a6b-244">Zauważ, że element formatu w obszarze **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** został skonfigurowany do wprowadzania kodu IBAN konta dostawcy w pliku płatności.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![Element BankIBAN na stronie Projektant formatów](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="b3a6b-246">Dodatek 2: konfigurowanie modułu Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="b3a6b-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="b3a6b-247">Modyfikowanie właściwości dostawcy</span><span class="sxs-lookup"><span data-stu-id="b3a6b-247">Modify a vendor property</span></span>

1. <span data-ttu-id="b3a6b-248">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Dostawcy** \> **Wszyscy dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="b3a6b-249">Wybierz dostawcę **DE-01002**, a następnie w okienku akcji na karcie **Dostawca** w grupie **Konfiguracja** wybierz pozycję **Konta bankowe**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="b3a6b-250">Na skróconej karcie **Identyfikacja** w polu **IBAN** <a name="enteredIBANcode"></a>wprowadź ciąg **GB33 BUKB 2020 1555 5555 55**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="b3a6b-251">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-251">Select **Save**.</span></span>

![Ustawione pole IBAN na stronie Konta bankowe dostawcy](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="b3a6b-253">Konfigurowanie metody płatności</span><span class="sxs-lookup"><span data-stu-id="b3a6b-253">Set up a method of payment</span></span>

1. <span data-ttu-id="b3a6b-254">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Ustawienia płatności** \> **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="b3a6b-255">Wybierz metodę płatności **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="b3a6b-256">Na skróconej karcie **Formaty plików** w sekcji **Formaty plików** ustaw opcję **Ogólny elektroniczny format eksportu** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="b3a6b-257">W polu **Konfiguracja formatu eksportu** wybierz format ER **Polecenie przelewu ISO20022**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="b3a6b-258">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-258">Select **Save**.</span></span>

![Ustawienia formatu pliku na stronie Metody płatności](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="b3a6b-260">Dodawanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="b3a6b-260">Add a vendor payment</span></span>

1. <span data-ttu-id="b3a6b-261">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="b3a6b-262">Dodaj nowy arkusz płatności.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="b3a6b-263">Wybierz pozycję **Wiersze** i dodaj nowy wiersz płatności.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="b3a6b-264">W polu **Konto** wybierz dostawcę **DE-01002**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="b3a6b-265">W polu **Debet** wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="b3a6b-266">W polu **Metoda płatności** wybierz pozycję **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="b3a6b-267">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-267">Select **Save**.</span></span>

![Płatność dostawcy dodana na stronie Płatności dostawcy](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="b3a6b-269">Dodatek 3: przetwarzanie płatności dostawcy</span><span class="sxs-lookup"><span data-stu-id="b3a6b-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="b3a6b-270">Przejdź do pozycji **Rozrachunki z dostawcami** \> **Płatności** \> **Arkusz płatności dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="b3a6b-271">Na stronie **Arkusz płatności dostawców** wybierz utworzony wcześniej arkusz płatności, a następnie wybierz pozycję **Wiersze**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="b3a6b-272">Wybierz wiersz płatności, a następnie wybierz pozycję **Stan płatności** \> **Brak**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="b3a6b-273">Wybierz **Generuj płatności**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="b3a6b-274">W polu **Metoda płatności** wybierz pozycję **SEPA CT**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="b3a6b-275">W polu **Konto bankowe** wybierz pozycję **DEMF OPER**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="b3a6b-276">W oknie dialogowym **Generowanie płatności** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="b3a6b-277">W oknie dialogowym **Parametry raportu elektronicznego** wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a6b-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]