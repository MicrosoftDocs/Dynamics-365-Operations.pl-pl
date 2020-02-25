---
title: Konfigurowanie integracji z rozwiązaniem Dayforce
description: Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule. Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 85e7274b0e9c130e5c3426fd1fff98410f93e49a
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010158"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="784c4-104">Konfigurowanie integracji z rozwiązaniem Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-104">Configure integration with Dayforce</span></span>

<span data-ttu-id="784c4-105">Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="784c4-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="784c4-106">Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="784c4-107">Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="784c4-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="784c4-108">Integracja wymaga określonych danych z programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="784c4-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="784c4-109">W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Human Resources w sposób zapewniający obsługę integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="784c4-110">Integracja wykorzystuje następujące ogólne kategorie danych:</span><span class="sxs-lookup"><span data-stu-id="784c4-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="784c4-111">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="784c4-111">Human resources data</span></span>
- <span data-ttu-id="784c4-112">Dane o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="784c4-112">Compensation data</span></span>
- <span data-ttu-id="784c4-113">Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="784c4-114">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="784c4-114">Worker data</span></span>

<span data-ttu-id="784c4-115">W tym artykule opisano czynności, które należy wykonać, aby włączyć integrację.</span><span class="sxs-lookup"><span data-stu-id="784c4-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="784c4-116">Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.</span><span class="sxs-lookup"><span data-stu-id="784c4-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="784c4-117">Włączanie integracji</span><span class="sxs-lookup"><span data-stu-id="784c4-117">Enable the integration</span></span>

<span data-ttu-id="784c4-118">W aplikacji Human Resources należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="784c4-119">Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do usługi Microsoft Dynamics 365 Finance, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="784c4-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="784c4-120">Aby włączyć integrację w aplikacji Human Resources, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="784c4-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="784c4-121">Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.</span><span class="sxs-lookup"><span data-stu-id="784c4-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="784c4-122">Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="784c4-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="784c4-123">Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="784c4-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="784c4-124">Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="784c4-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="784c4-125">Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="784c4-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="784c4-126">W razie potrzeby można zmienić tę częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="784c4-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="784c4-127">Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące artykuły poświęcone usłudze Azure:</span><span class="sxs-lookup"><span data-stu-id="784c4-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="784c4-128">Konta magazynu w usłudze Azure — informacje</span><span class="sxs-lookup"><span data-stu-id="784c4-128">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="784c4-129">Konfigurowanie ciągów połączeń z usługą Azure Storage</span><span class="sxs-lookup"><span data-stu-id="784c4-129">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="784c4-130">Dane techniczne, gdy integracja listy płac jest włączona</span><span class="sxs-lookup"><span data-stu-id="784c4-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="784c4-131">Włączenie integracji listy płac ma dwa główne skutki:</span><span class="sxs-lookup"><span data-stu-id="784c4-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="784c4-132">Zostanie utworzony projekt eksportu danych o nazwie „Eksport integracji list płac”.</span><span class="sxs-lookup"><span data-stu-id="784c4-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="784c4-133">Ten projekt zawiera podmioty i pola wymagane do integracji listy płac.</span><span class="sxs-lookup"><span data-stu-id="784c4-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="784c4-134">Aby sprawdzić projekt, przejdź do **Administracja systemu**, wybierz kafelek **Zarządzanie danymi**, a następnie otwórz projekt danych z listy projektów.</span><span class="sxs-lookup"><span data-stu-id="784c4-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="784c4-135">To zadanie wsadowe wykonuje projekt eksportu danych, szyfruje otrzymany pakiet danych i przesyła plik pakietu danych do punktu końcowego SFTP skonfigurowanego na ekranie **Integracja konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="784c4-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="784c4-136">Pakiet danych przesłany do punktu końcowego SFTP jest szyfrowany przy użyciu klucza unikalnego dla pakietu.</span><span class="sxs-lookup"><span data-stu-id="784c4-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="784c4-137">Klucz to Azure Key Vault dostępny jedynie przez Ceridian.</span><span class="sxs-lookup"><span data-stu-id="784c4-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="784c4-138">Nie jest możliwe odszyfrowanie i sprawdzenie zawartości pakietu danych.</span><span class="sxs-lookup"><span data-stu-id="784c4-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="784c4-139">Jeśli chcesz sprawdzić zawartość pakietu danych, musisz ręcznie wyeksportować projekt danych „Eksportu integracji płac”, pobrać go, a następnie otworzyć.</span><span class="sxs-lookup"><span data-stu-id="784c4-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="784c4-140">Ręczny eksport nie zastosuje szyfrowania ani nie dokona transferu pakietu.</span><span class="sxs-lookup"><span data-stu-id="784c4-140">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="784c4-141">Konfigurowanie danych</span><span class="sxs-lookup"><span data-stu-id="784c4-141">Configure your data</span></span> 

<span data-ttu-id="784c4-142">Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="784c4-142">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="784c4-143">Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="784c4-143">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="784c4-144">Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-144">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="784c4-145">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="784c4-145">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="784c4-146">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="784c4-146">Benefits</span></span> 

<span data-ttu-id="784c4-147">Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="784c4-147">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="784c4-148">Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-148">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="784c4-149">Plany świadczeń</span><span class="sxs-lookup"><span data-stu-id="784c4-149">Benefit plans</span></span>

- <span data-ttu-id="784c4-150">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-150">Plan (required)</span></span>
- <span data-ttu-id="784c4-151">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-151">Type (required)</span></span>
- <span data-ttu-id="784c4-152">Wpływ na listę płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-152">Payroll impact (required)</span></span>
- <span data-ttu-id="784c4-153">Odzyskaj zaległości</span><span class="sxs-lookup"><span data-stu-id="784c4-153">Recover arrears</span></span>
- <span data-ttu-id="784c4-154">Metoda potrącenia</span><span class="sxs-lookup"><span data-stu-id="784c4-154">Deduction method</span></span>
- <span data-ttu-id="784c4-155">Priorytet potrącenia</span><span class="sxs-lookup"><span data-stu-id="784c4-155">Deduction priority</span></span>
- <span data-ttu-id="784c4-156">Okres limitu</span><span class="sxs-lookup"><span data-stu-id="784c4-156">Limit period</span></span>
- <span data-ttu-id="784c4-157">Kwota limitu</span><span class="sxs-lookup"><span data-stu-id="784c4-157">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="784c4-158">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="784c4-158">Benefits</span></span>

- <span data-ttu-id="784c4-159">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-159">Plan (required)</span></span>
- <span data-ttu-id="784c4-160">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-160">Type (required)</span></span>
- <span data-ttu-id="784c4-161">Opcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-161">Option (required)</span></span>
- <span data-ttu-id="784c4-162">Identyfikator świadczenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-162">Benefit ID (required)</span></span>
- <span data-ttu-id="784c4-163">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="784c4-163">Frequency</span></span>
- <span data-ttu-id="784c4-164">Podstawa</span><span class="sxs-lookup"><span data-stu-id="784c4-164">Basis</span></span>
- <span data-ttu-id="784c4-165">Kwota lub stawka</span><span class="sxs-lookup"><span data-stu-id="784c4-165">Amount or rate</span></span>
- <span data-ttu-id="784c4-166">Kod zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-166">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="784c4-167">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="784c4-167">Supported frequencies</span></span> 

- <span data-ttu-id="784c4-168">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="784c4-168">Weekly</span></span>
- <span data-ttu-id="784c4-169">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="784c4-169">Bi-weekly</span></span>
- <span data-ttu-id="784c4-170">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="784c4-170">Semi-monthly</span></span>
- <span data-ttu-id="784c4-171">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="784c4-171">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="784c4-172">Obsługiwane podstawy</span><span class="sxs-lookup"><span data-stu-id="784c4-172">Supported bases</span></span> 

- <span data-ttu-id="784c4-173">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="784c4-173">Fixed amount</span></span>
- <span data-ttu-id="784c4-174">Procent zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-174">Percent of earnings</span></span>
- <span data-ttu-id="784c4-175">Godziny płatne</span><span class="sxs-lookup"><span data-stu-id="784c4-175">Productive hours</span></span>

<span data-ttu-id="784c4-176">System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="784c4-176">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="784c4-177">Przeglądanie zadań w Human Resources</span><span class="sxs-lookup"><span data-stu-id="784c4-177">Selection in Human Resources</span></span>        | <span data-ttu-id="784c4-178">Wynik w systemie Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-178">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="784c4-179">Brak</span><span class="sxs-lookup"><span data-stu-id="784c4-179">None</span></span>                       | <span data-ttu-id="784c4-180">Nie jest tworzone żadne potrącenie</span><span class="sxs-lookup"><span data-stu-id="784c4-180">No deduction is created.</span></span>                      |
| <span data-ttu-id="784c4-181">Tylko potrącenie</span><span class="sxs-lookup"><span data-stu-id="784c4-181">Deduction only</span></span>             | <span data-ttu-id="784c4-182">Jest tworzone potrącenie od pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-182">An employee deduction is created.</span></span>             |
| <span data-ttu-id="784c4-183">Tylko udział</span><span class="sxs-lookup"><span data-stu-id="784c4-183">Contribution only</span></span>          | <span data-ttu-id="784c4-184">Jest tworzone potrącenie od pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="784c4-184">An employer deduction is created.</span></span>             |
| <span data-ttu-id="784c4-185">Potrącenie i udział</span><span class="sxs-lookup"><span data-stu-id="784c4-185">Deduction and contribution</span></span> | <span data-ttu-id="784c4-186">Są tworzone potrącenia od pracownika i pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="784c4-186">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="784c4-187">Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="784c4-187">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="784c4-188">Dostarczanie programu świadczeń dla pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="784c4-188">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="784c4-189">Utwórz nowe świadczenie</span><span class="sxs-lookup"><span data-stu-id="784c4-189">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="784c4-190">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="784c4-190">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="784c4-191">Rejestrowanie i usuwanie świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="784c4-191">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="784c4-192">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="784c4-192">Compensation</span></span> 

<span data-ttu-id="784c4-193">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="784c4-193">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="784c4-194">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="784c4-194">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="784c4-195">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="784c4-195">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="784c4-196">Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-196">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="784c4-197">Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-197">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="784c4-198">Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="784c4-198">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="784c4-199">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="784c4-199">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="784c4-200">Tworzenie planów stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="784c4-200">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="784c4-201">Tworzenie planów wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="784c4-201">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="784c4-202">Opracowywanie struktury i planu pensji/wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="784c4-202">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="784c4-203">Przetwarzanie wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="784c4-203">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="784c4-204">Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników</span><span class="sxs-lookup"><span data-stu-id="784c4-204">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="784c4-205">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="784c4-205">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="784c4-206">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="784c4-206">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="784c4-207">Funkcje</span><span class="sxs-lookup"><span data-stu-id="784c4-207">Jobs</span></span> 

<span data-ttu-id="784c4-208">Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję.</span><span class="sxs-lookup"><span data-stu-id="784c4-208">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="784c4-209">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="784c4-209">For more information, see the following articles:</span></span>

- [<span data-ttu-id="784c4-210">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="784c4-210">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="784c4-211">Definiowanie nowych funkcji</span><span class="sxs-lookup"><span data-stu-id="784c4-211">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="784c4-212">Pozycje</span><span class="sxs-lookup"><span data-stu-id="784c4-212">Positions</span></span>

<span data-ttu-id="784c4-213">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="784c4-213">A position is an individual instance of a job.</span></span> <span data-ttu-id="784c4-214">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="784c4-214">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="784c4-215">Stanowisko istnieje w dziale.</span><span class="sxs-lookup"><span data-stu-id="784c4-215">A position exists in a department.</span></span> <span data-ttu-id="784c4-216">Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="784c4-216">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="784c4-217">Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="784c4-217">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="784c4-218">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-218">Position (required)</span></span>
- <span data-ttu-id="784c4-219">Opis (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-219">Description (required)</span></span>
- <span data-ttu-id="784c4-220">Funkcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-220">Job (required)</span></span>
- <span data-ttu-id="784c4-221">Dział (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-221">Department (required)</span></span>
- <span data-ttu-id="784c4-222">Typ stanowiska (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-222">Position type (required)</span></span>
- <span data-ttu-id="784c4-223">W przeliczeniu na pełne etaty</span><span class="sxs-lookup"><span data-stu-id="784c4-223">Full-time equivalent</span></span>
- <span data-ttu-id="784c4-224">Zwykłe godziny (rocznie) (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-224">Annual regular hours (required)</span></span>
- <span data-ttu-id="784c4-225">Zapłacone przez firmę (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-225">Paid by legal entity (required)</span></span>
- <span data-ttu-id="784c4-226">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-226">Pay cycle (required)</span></span>
- <span data-ttu-id="784c4-227">Domyślny wymiar finansowy — Centrum kosztu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-227">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="784c4-228">Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="784c4-228">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="784c4-229">Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-229">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="784c4-230">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="784c4-230">For more information, see the following articles:</span></span>

- [<span data-ttu-id="784c4-231">Organizowanie pracowników za pomocą działów, funkcji i stanowisk</span><span class="sxs-lookup"><span data-stu-id="784c4-231">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="784c4-232">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="784c4-232">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="784c4-233">Działy</span><span class="sxs-lookup"><span data-stu-id="784c4-233">Departments</span></span>

<span data-ttu-id="784c4-234">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="784c4-234">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="784c4-235">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="784c4-235">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="784c4-236">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="784c4-236">You can use departments to report on functional areas.</span></span> <span data-ttu-id="784c4-237">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="784c4-237">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="784c4-238">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="784c4-238">For more information, see the following articles:</span></span>

- [<span data-ttu-id="784c4-239">Tworzenie działu i kojarzenie go z hierarchią działów</span><span class="sxs-lookup"><span data-stu-id="784c4-239">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="784c4-240">Definiowanie nowych działów</span><span class="sxs-lookup"><span data-stu-id="784c4-240">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="784c4-241">Cykle płac i okresy płac</span><span class="sxs-lookup"><span data-stu-id="784c4-241">Pay cycles and pay periods</span></span>

<span data-ttu-id="784c4-242">Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="784c4-242">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="784c4-243">Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="784c4-243">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="784c4-244">Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="784c4-244">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="784c4-245">Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="784c4-245">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="784c4-246">Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu.</span><span class="sxs-lookup"><span data-stu-id="784c4-246">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="784c4-247">Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach.</span><span class="sxs-lookup"><span data-stu-id="784c4-247">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="784c4-248">Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.</span><span class="sxs-lookup"><span data-stu-id="784c4-248">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="784c4-249">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="784c4-249">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="784c4-250">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-250">Pay cycle (required)</span></span>
- <span data-ttu-id="784c4-251">Częstotliwość cyklu kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-251">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="784c4-252">Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="784c4-252">Period start date (first pay period required)</span></span>
- <span data-ttu-id="784c4-253">Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="784c4-253">Default payment date (first pay period required)</span></span>

<span data-ttu-id="784c4-254">Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="784c4-254">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="784c4-255">Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="784c4-255">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="784c4-256">System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="784c4-256">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="784c4-257">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-257">Earning codes</span></span>

<span data-ttu-id="784c4-258">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="784c4-258">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="784c4-259">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="784c4-259">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="784c4-260">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="784c4-260">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="784c4-261">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-261">Earning Code (required)</span></span>
- <span data-ttu-id="784c4-262">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-262">Description</span></span>
- <span data-ttu-id="784c4-263">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="784c4-263">Unit of measure</span></span>
- <span data-ttu-id="784c4-264">Płatne</span><span class="sxs-lookup"><span data-stu-id="784c4-264">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="784c4-265">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="784c4-265">Worker data</span></span>

<span data-ttu-id="784c4-266">Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych.</span><span class="sxs-lookup"><span data-stu-id="784c4-266">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="784c4-267">Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="784c4-267">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="784c4-268">Można przechowywać następujące informacje o pracownikach:</span><span class="sxs-lookup"><span data-stu-id="784c4-268">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="784c4-269">**Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.</span><span class="sxs-lookup"><span data-stu-id="784c4-269">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="784c4-270">**Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="784c4-270">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="784c4-271">**Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.</span><span class="sxs-lookup"><span data-stu-id="784c4-271">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="784c4-272">**Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="784c4-272">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="784c4-273">Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-273">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="784c4-274">Informacje ogólne</span><span class="sxs-lookup"><span data-stu-id="784c4-274">General information</span></span>

- <span data-ttu-id="784c4-275">Numer pracownika (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-275">Personnel number (required)</span></span>
- <span data-ttu-id="784c4-276">Imię (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-276">First name (required)</span></span>
- <span data-ttu-id="784c4-277">Nazwisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-277">Last name (required)</span></span>
- <span data-ttu-id="784c4-278">Drugie imię</span><span class="sxs-lookup"><span data-stu-id="784c4-278">Middle name</span></span>
- <span data-ttu-id="784c4-279">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="784c4-279">Seniority date</span></span>
- <span data-ttu-id="784c4-280">Znane jako</span><span class="sxs-lookup"><span data-stu-id="784c4-280">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="784c4-281">Informacje osobiste</span><span class="sxs-lookup"><span data-stu-id="784c4-281">Personal information</span></span>

- <span data-ttu-id="784c4-282">Stan cywilny (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-282">Marital status (required)</span></span>
- <span data-ttu-id="784c4-283">Data urodzenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-283">Birth date (required)</span></span>
- <span data-ttu-id="784c4-284">Płeć (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-284">Gender (required)</span></span>
- <span data-ttu-id="784c4-285">Osoba niepełnosprawna</span><span class="sxs-lookup"><span data-stu-id="784c4-285">Person with disabilities</span></span>
- <span data-ttu-id="784c4-286">Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="784c4-286">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="784c4-287">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="784c4-287">Address information</span></span>

- <span data-ttu-id="784c4-288">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-288">Primary (required)</span></span>
- <span data-ttu-id="784c4-289">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-289">Country/region (required)</span></span>
- <span data-ttu-id="784c4-290">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-290">Postal code (required)</span></span>
- <span data-ttu-id="784c4-291">Numer domu (wymagane) (jedynie w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="784c4-291">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="784c4-292">Dodatkowe określenie budynku (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="784c4-292">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="784c4-293">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-293">City (required)</span></span>
- <span data-ttu-id="784c4-294">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-294">State (required)</span></span>
- <span data-ttu-id="784c4-295">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-295">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="784c4-296">Informacje o kontakcie</span><span class="sxs-lookup"><span data-stu-id="784c4-296">Contact information</span></span> 

- <span data-ttu-id="784c4-297">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-297">Primary (required)</span></span>
- <span data-ttu-id="784c4-298">Nazwa osoby kontaktowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-298">Contact number (required)</span></span>
- <span data-ttu-id="784c4-299">Wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="784c4-299">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="784c4-300">Informacje płacowe i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-300">Payroll information and earning codes</span></span>

<span data-ttu-id="784c4-301">Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="784c4-301">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="784c4-302">Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="784c4-302">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="784c4-303">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-303">Earning codes</span></span>

- <span data-ttu-id="784c4-304">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-304">Position (required)</span></span>
- <span data-ttu-id="784c4-305">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-305">Earning Code (required)</span></span>
- <span data-ttu-id="784c4-306">Częstotliwość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-306">Frequency (required)</span></span>
- <span data-ttu-id="784c4-307">Kwota (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-307">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="784c4-308">Informacje listy płac</span><span class="sxs-lookup"><span data-stu-id="784c4-308">Payroll information</span></span>

- <span data-ttu-id="784c4-309">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="784c4-309">Payment Method</span></span>
- <span data-ttu-id="784c4-310">Region gospodarczy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-310">Economic Region (required)</span></span>
- <span data-ttu-id="784c4-311">Identyfikator świadczeń pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="784c4-311">Employee Benefits ID</span></span>
- <span data-ttu-id="784c4-312">Numer dowodu osobistego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-312">National ID Number (required)</span></span>
- <span data-ttu-id="784c4-313">Numer książeczki wojskowej</span><span class="sxs-lookup"><span data-stu-id="784c4-313">Military Service Number</span></span>
- <span data-ttu-id="784c4-314">Identyfikator zmiany (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-314">Shift ID (required)</span></span>
- <span data-ttu-id="784c4-315">Numer identyfikacji podatkowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-315">Tax Number (required)</span></span>
- <span data-ttu-id="784c4-316">Identyfikator związku (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-316">Union ID (required)</span></span>
- <span data-ttu-id="784c4-317">Identyfikator dnia roboczego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-317">Work Day ID (required)</span></span>
- <span data-ttu-id="784c4-318">Numer pozwolenia na pracę</span><span class="sxs-lookup"><span data-stu-id="784c4-318">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="784c4-319">W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="784c4-319">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="784c4-320">Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.</span><span class="sxs-lookup"><span data-stu-id="784c4-320">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="784c4-321">Szczegóły zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-321">Employment details</span></span>

<span data-ttu-id="784c4-322">Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-322">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="784c4-323">W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.</span><span class="sxs-lookup"><span data-stu-id="784c4-323">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="784c4-324">Data rozpoczęcia zatrudnienia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-324">Employment start date (required)</span></span>
- <span data-ttu-id="784c4-325">Data zakończenia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-325">Employment end date</span></span>
- <span data-ttu-id="784c4-326">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="784c4-326">Start date</span></span>
- <span data-ttu-id="784c4-327">Dopasowana data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="784c4-327">Adjusted start date</span></span>
- <span data-ttu-id="784c4-328">Data zakończenia (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="784c4-328">Termination date (required upon termination)</span></span>
- <span data-ttu-id="784c4-329">Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="784c4-329">Termination reason (required upon termination)</span></span>

<span data-ttu-id="784c4-330">Kluczowe daty pracownika są obliczane na podstawie następujących informacji.</span><span class="sxs-lookup"><span data-stu-id="784c4-330">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="784c4-331">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-331">Human Resources</span></span>                | <span data-ttu-id="784c4-332">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-332">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="784c4-333">Ostatnia data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-333">Most recent hire date</span></span> | <span data-ttu-id="784c4-334">Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-334">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="784c4-335">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="784c4-335">Termination date</span></span>      | <span data-ttu-id="784c4-336">Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-336">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="784c4-337">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="784c4-337">Start date</span></span>            | <span data-ttu-id="784c4-338">Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-338">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="784c4-339">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-339">Original hire date</span></span>    | <span data-ttu-id="784c4-340">Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-340">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="784c4-341">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="784c4-341">Compensation</span></span>

<span data-ttu-id="784c4-342">Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="784c4-342">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="784c4-343">Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="784c4-343">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="784c4-344">Data obowiązywania (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-344">Effective Date (required)</span></span>
- <span data-ttu-id="784c4-345">Data ważności</span><span class="sxs-lookup"><span data-stu-id="784c4-345">Expiration date</span></span>
- <span data-ttu-id="784c4-346">Stawka płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-346">Pay Rate (required)</span></span>
- <span data-ttu-id="784c4-347">Konwersje stawek płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-347">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="784c4-348">Równowartość roczna (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-348">Annual equivalent (required)</span></span>
- <span data-ttu-id="784c4-349">Równowartość godzinowa (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-349">Hourly equivalent (required)</span></span>

<span data-ttu-id="784c4-350">Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-350">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="784c4-351">Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-351">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="784c4-352">Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-352">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="784c4-353">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="784c4-353">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="784c4-354">Numer ubezpieczenia społecznego</span><span class="sxs-lookup"><span data-stu-id="784c4-354">Social Security identifier</span></span> 

<span data-ttu-id="784c4-355">Każdy pracownik musi mieć jeden identyfikator podstawowy.</span><span class="sxs-lookup"><span data-stu-id="784c4-355">Every employee must have one primary identifier.</span></span> <span data-ttu-id="784c4-356">Identyfikator ten musi być typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="784c4-356">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="784c4-357">W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="784c4-357">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="784c4-358">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-358">Primary (required)</span></span>
- <span data-ttu-id="784c4-359">Typ identyfikacji = „PESEL”</span><span class="sxs-lookup"><span data-stu-id="784c4-359">Identification Type = "SSN"</span></span>
- <span data-ttu-id="784c4-360">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="784c4-360">Issued Date</span></span>
- <span data-ttu-id="784c4-361">Data ważności</span><span class="sxs-lookup"><span data-stu-id="784c4-361">Expiration Date</span></span>

<span data-ttu-id="784c4-362">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="784c4-362">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="784c4-363">Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.</span><span class="sxs-lookup"><span data-stu-id="784c4-363">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="784c4-364">Konta bankowe i wypłaty</span><span class="sxs-lookup"><span data-stu-id="784c4-364">Bank accounts and disbursements</span></span>

<span data-ttu-id="784c4-365">Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="784c4-365">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="784c4-366">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-366">Human Resources</span></span>                         | <span data-ttu-id="784c4-367">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-367">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="784c4-368">Numer konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-368">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="784c4-369">Kod SWIFT (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-369">SWIFT code (required)</span></span>          | <span data-ttu-id="784c4-370">Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="784c4-370">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="784c4-371">Numer oddziału (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-371">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="784c4-372">Typ konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-372">Bank account type (required)</span></span>   | <span data-ttu-id="784c4-373">Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="784c4-373">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="784c4-374">Obsługiwane wartości **Czekowe** i **Lista płac**.</span><span class="sxs-lookup"><span data-stu-id="784c4-374">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="784c4-375">Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku.</span><span class="sxs-lookup"><span data-stu-id="784c4-375">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="784c4-376">Wszystkie inne konta pozostałości są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="784c4-376">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="784c4-377">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="784c4-377">Address information</span></span>

<span data-ttu-id="784c4-378">Każdy pracownik musi mieć jedną lokalizację podstawową.</span><span class="sxs-lookup"><span data-stu-id="784c4-378">Every employee must have one primary location.</span></span> <span data-ttu-id="784c4-379">W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="784c4-379">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="784c4-380">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-380">Primary (required)</span></span>
- <span data-ttu-id="784c4-381">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-381">Country/region (required)</span></span>
- <span data-ttu-id="784c4-382">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-382">Zip/postal code (required)</span></span>
- <span data-ttu-id="784c4-383">Ulica (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-383">Street (required)</span></span>
- <span data-ttu-id="784c4-384">Numer domu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-384">Street Number (required)</span></span>
- <span data-ttu-id="784c4-385">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="784c4-385">Building Complement</span></span>
- <span data-ttu-id="784c4-386">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-386">City (required)</span></span>
- <span data-ttu-id="784c4-387">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-387">State (required)</span></span>
- <span data-ttu-id="784c4-388">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-388">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="784c4-389">Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie</span><span class="sxs-lookup"><span data-stu-id="784c4-389">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="784c4-390">Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="784c4-390">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="784c4-391">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="784c4-391">Departments are required on positions.</span></span>
- <span data-ttu-id="784c4-392">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="784c4-392">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="784c4-393">Można skonfigurować Human Resources tak, aby Stanowiska umożliwiały określenie działu.</span><span class="sxs-lookup"><span data-stu-id="784c4-393">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="784c4-394">Aby to zrobić, przejdź do **stanowisk udostępnionych zasobów ludzkich > Stanowisk > wymagają działów stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="784c4-394">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="784c4-395">Zaleca się, aby to ustawienie zostało wymuszone dla integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-395">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="784c4-396">Typy funkcji</span><span class="sxs-lookup"><span data-stu-id="784c4-396">Job types</span></span>

<span data-ttu-id="784c4-397">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="784c4-397">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="784c4-398">Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie.</span><span class="sxs-lookup"><span data-stu-id="784c4-398">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="784c4-399">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="784c4-399">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="784c4-400">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="784c4-400">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="784c4-401">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-401">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="784c4-402">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="784c4-402">Job type</span></span>   | <span data-ttu-id="784c4-403">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-403">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="784c4-404">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="784c4-404">Hourly</span></span>     | <span data-ttu-id="784c4-405">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="784c4-405">Hourly</span></span>      |
| <span data-ttu-id="784c4-406">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="784c4-406">Salaried</span></span>   | <span data-ttu-id="784c4-407">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="784c4-407">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="784c4-408">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="784c4-408">Position types</span></span> 

<span data-ttu-id="784c4-409">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="784c4-409">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="784c4-410">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="784c4-410">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="784c4-411">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-411">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="784c4-412">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="784c4-412">Position type</span></span>   | <span data-ttu-id="784c4-413">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-413">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="784c4-414">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="784c4-414">Full-time</span></span>       | <span data-ttu-id="784c4-415">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="784c4-415">Full time employee</span></span> |
| <span data-ttu-id="784c4-416">Część etatu</span><span class="sxs-lookup"><span data-stu-id="784c4-416">Part-time</span></span>       | <span data-ttu-id="784c4-417">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="784c4-417">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="784c4-418">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="784c4-418">Reason codes</span></span>

<span data-ttu-id="784c4-419">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-419">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="784c4-420">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-420">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="784c4-421">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-421">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="784c4-422">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="784c4-422">Reason code</span></span>    | <span data-ttu-id="784c4-423">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-423">Description</span></span>      | <span data-ttu-id="784c4-424">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="784c4-424">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="784c4-425">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="784c4-425">RESIGNATION</span></span>    | <span data-ttu-id="784c4-426">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="784c4-426">Resignation</span></span>      | <span data-ttu-id="784c4-427">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-427">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-428">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="784c4-428">TERMINATION</span></span>    | <span data-ttu-id="784c4-429">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="784c4-429">Termination</span></span>      | <span data-ttu-id="784c4-430">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-430">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-431">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="784c4-431">RETIREMENT</span></span>     | <span data-ttu-id="784c4-432">Emerytura</span><span class="sxs-lookup"><span data-stu-id="784c4-432">Retirement</span></span>       | <span data-ttu-id="784c4-433">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-433">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-434">INNY</span><span class="sxs-lookup"><span data-stu-id="784c4-434">OTHER</span></span>          | <span data-ttu-id="784c4-435">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="784c4-435">Other Reasons</span></span>    | <span data-ttu-id="784c4-436">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-436">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-437">DEATH</span><span class="sxs-lookup"><span data-stu-id="784c4-437">DEATH</span></span>          | <span data-ttu-id="784c4-438">Śmierć</span><span class="sxs-lookup"><span data-stu-id="784c4-438">Death</span></span>            | <span data-ttu-id="784c4-439">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-439">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-440">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="784c4-440">LEAVEOFABSENCE</span></span> | <span data-ttu-id="784c4-441">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="784c4-441">Leave of Absence</span></span> | <span data-ttu-id="784c4-442">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-442">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-443">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="784c4-443">CONTRACTEND</span></span>    | <span data-ttu-id="784c4-444">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="784c4-444">End of Contract</span></span>  | <span data-ttu-id="784c4-445">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-445">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-446">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="784c4-446">SALARYCHANGE</span></span>   | <span data-ttu-id="784c4-447">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="784c4-447">Change of Salary</span></span> | <span data-ttu-id="784c4-448">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="784c4-448">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="784c4-449">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="784c4-449">Marital status</span></span>

<span data-ttu-id="784c4-450">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-450">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="784c4-451">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-451">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="784c4-452">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-452">Human Resources</span></span>                 | <span data-ttu-id="784c4-453">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-453">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="784c4-454">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="784c4-454">Married</span></span>                | <span data-ttu-id="784c4-455">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="784c4-455">Married</span></span>              |
| <span data-ttu-id="784c4-456">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="784c4-456">Single</span></span>                 | <span data-ttu-id="784c4-457">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="784c4-457">Single</span></span>               |
| <span data-ttu-id="784c4-458">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="784c4-458">Widowed</span></span>                | <span data-ttu-id="784c4-459">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="784c4-459">Widowed</span></span>              |
| <span data-ttu-id="784c4-460">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="784c4-460">Divorced</span></span>               | <span data-ttu-id="784c4-461">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="784c4-461">Divorced</span></span>             |
| <span data-ttu-id="784c4-462">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="784c4-462">Registered Partnership</span></span> | <span data-ttu-id="784c4-463">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="784c4-463">Domestic Partnership</span></span> |
| <span data-ttu-id="784c4-464">None</span><span class="sxs-lookup"><span data-stu-id="784c4-464">None</span></span>                   | <span data-ttu-id="784c4-465">None</span><span class="sxs-lookup"><span data-stu-id="784c4-465">None</span></span>                 |
| <span data-ttu-id="784c4-466">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="784c4-466">Cohabiting</span></span>             | <span data-ttu-id="784c4-467">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="784c4-467">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="784c4-468">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="784c4-468">Gender</span></span>

<span data-ttu-id="784c4-469">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-469">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="784c4-470">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-470">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="784c4-471">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-471">Human Resources</span></span>       | <span data-ttu-id="784c4-472">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-472">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="784c4-473">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="784c4-473">Male</span></span>         | <span data-ttu-id="784c4-474">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="784c4-474">Male</span></span>            |
| <span data-ttu-id="784c4-475">Kobieta</span><span class="sxs-lookup"><span data-stu-id="784c4-475">Female</span></span>       | <span data-ttu-id="784c4-476">Kobieta</span><span class="sxs-lookup"><span data-stu-id="784c4-476">Female</span></span>          |
| <span data-ttu-id="784c4-477">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="784c4-477">Non-specific</span></span> | <span data-ttu-id="784c4-478">*Nieobsługiwane*</span><span class="sxs-lookup"><span data-stu-id="784c4-478">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="784c4-479">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-479">Earning codes</span></span>

<span data-ttu-id="784c4-480">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="784c4-480">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="784c4-481">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="784c4-481">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="784c4-482">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="784c4-482">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="784c4-483">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="784c4-483">Supported frequencies</span></span>

- <span data-ttu-id="784c4-484">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="784c4-484">All</span></span>
- <span data-ttu-id="784c4-485">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="784c4-485">EVERYPAY</span></span>
- <span data-ttu-id="784c4-486">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="784c4-486">EACHPAYPERIOD</span></span>
- <span data-ttu-id="784c4-487">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="784c4-487">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="784c4-488">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="784c4-488">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="784c4-489">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-489">1OFMTH</span></span>
- <span data-ttu-id="784c4-490">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-490">LASTOFMTH</span></span>
- <span data-ttu-id="784c4-491">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-491">2OFMTH</span></span>
- <span data-ttu-id="784c4-492">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-492">3OFMTH</span></span>
- <span data-ttu-id="784c4-493">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-493">4OFMTH</span></span>
- <span data-ttu-id="784c4-494">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-494">5OFMTH</span></span>
- <span data-ttu-id="784c4-495">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-495">1N2OFMTH</span></span>
- <span data-ttu-id="784c4-496">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-496">3N4OFMTH</span></span>
- <span data-ttu-id="784c4-497">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-497">1N3OFMTH</span></span>
- <span data-ttu-id="784c4-498">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-498">1N4OFMTH</span></span>
- <span data-ttu-id="784c4-499">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-499">2N3OFMTH</span></span>
- <span data-ttu-id="784c4-500">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-500">2N4OFMTH</span></span>
- <span data-ttu-id="784c4-501">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-501">1N2N3OFMTH</span></span>
- <span data-ttu-id="784c4-502">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-502">1N2N4OFMTH</span></span>
- <span data-ttu-id="784c4-503">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-503">1N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-504">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-504">2N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-505">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-505">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-506">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="784c4-506">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="784c4-507">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-507">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="784c4-508">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-508">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="784c4-509">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-509">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="784c4-510">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-510">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="784c4-511">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-511">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="784c4-512">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-512">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="784c4-513">Adresy</span><span class="sxs-lookup"><span data-stu-id="784c4-513">Addresses</span></span>

<span data-ttu-id="784c4-514">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="784c4-514">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="784c4-515">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="784c4-515">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="784c4-516">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-516">Human Resources</span></span>          | <span data-ttu-id="784c4-517">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-517">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="784c4-518">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="784c4-518">Country/Region</span></span>  | <span data-ttu-id="784c4-519">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="784c4-519">Country Code</span></span>          |
| <span data-ttu-id="784c4-520">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="784c4-520">Zip/Postal Code</span></span> | <span data-ttu-id="784c4-521">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="784c4-521">Postal Code</span></span>           |
| <span data-ttu-id="784c4-522">Stanowy</span><span class="sxs-lookup"><span data-stu-id="784c4-522">State</span></span>           | <span data-ttu-id="784c4-523">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="784c4-523">State Code</span></span>            |
| <span data-ttu-id="784c4-524">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="784c4-524">City</span></span>            | <span data-ttu-id="784c4-525">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="784c4-525">City</span></span>                  |
| <span data-ttu-id="784c4-526">Powiat</span><span class="sxs-lookup"><span data-stu-id="784c4-526">County</span></span>          | <span data-ttu-id="784c4-527">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="784c4-527">County (Municipality)</span></span> |
| <span data-ttu-id="784c4-528">Ulica</span><span class="sxs-lookup"><span data-stu-id="784c4-528">Street</span></span>          | <span data-ttu-id="784c4-529">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="784c4-529">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="784c4-530">Regiony podatkowe</span><span class="sxs-lookup"><span data-stu-id="784c4-530">Tax regions</span></span>

<span data-ttu-id="784c4-531">Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac.</span><span class="sxs-lookup"><span data-stu-id="784c4-531">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="784c4-532">Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="784c4-532">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="784c4-533">Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-533">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="784c4-534">Region podatkowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-534">Tax region (required)</span></span>
- <span data-ttu-id="784c4-535">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-535">Country/Region (required)</span></span>
- <span data-ttu-id="784c4-536">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-536">State (required)</span></span>
- <span data-ttu-id="784c4-537">Powiat</span><span class="sxs-lookup"><span data-stu-id="784c4-537">County</span></span> 
- <span data-ttu-id="784c4-538">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="784c4-538">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="784c4-539">Konfigurowanie danych w celu generowania listy płac w Meksyku</span><span class="sxs-lookup"><span data-stu-id="784c4-539">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="784c4-540">Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="784c4-540">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="784c4-541">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="784c4-541">Departments are required on positions.</span></span>
- <span data-ttu-id="784c4-542">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="784c4-542">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="784c4-543">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="784c4-543">Job types</span></span>

<span data-ttu-id="784c4-544">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="784c4-544">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="784c4-545">Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="784c4-545">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="784c4-546">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="784c4-546">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="784c4-547">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="784c4-547">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="784c4-548">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-548">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="784c4-549">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="784c4-549">Job type</span></span>   | <span data-ttu-id="784c4-550">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-550">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="784c4-551">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="784c4-551">Hourly</span></span>     | <span data-ttu-id="784c4-552">MX Co godzinę</span><span class="sxs-lookup"><span data-stu-id="784c4-552">MX Hourly</span></span>   |
| <span data-ttu-id="784c4-553">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="784c4-553">Salaried</span></span>   | <span data-ttu-id="784c4-554">MX Stała pensja</span><span class="sxs-lookup"><span data-stu-id="784c4-554">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="784c4-555">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="784c4-555">Position types</span></span> 

<span data-ttu-id="784c4-556">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="784c4-556">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="784c4-557">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="784c4-557">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="784c4-558">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-558">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="784c4-559">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="784c4-559">Position type</span></span>   | <span data-ttu-id="784c4-560">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-560">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="784c4-561">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="784c4-561">Full-time</span></span>       | <span data-ttu-id="784c4-562">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="784c4-562">Full time employee</span></span> |
| <span data-ttu-id="784c4-563">Część etatu</span><span class="sxs-lookup"><span data-stu-id="784c4-563">Part-time</span></span>       | <span data-ttu-id="784c4-564">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="784c4-564">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="784c4-565">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="784c4-565">Reason codes</span></span>

<span data-ttu-id="784c4-566">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-566">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="784c4-567">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="784c4-567">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="784c4-568">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-568">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="784c4-569">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="784c4-569">Reason code</span></span>            | <span data-ttu-id="784c4-570">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-570">Description</span></span>                    | <span data-ttu-id="784c4-571">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="784c4-571">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="784c4-572">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="784c4-572">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="784c4-573">Odejście z pracy przed pierwszą wypłatą</span><span class="sxs-lookup"><span data-stu-id="784c4-573">Departure before first payroll</span></span> | <span data-ttu-id="784c4-574">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-574">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-575">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="784c4-575">RESIGNATION</span></span>            | <span data-ttu-id="784c4-576">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="784c4-576">Resignation</span></span>                    | <span data-ttu-id="784c4-577">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-577">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-578">PENSION</span><span class="sxs-lookup"><span data-stu-id="784c4-578">PENSION</span></span>                | <span data-ttu-id="784c4-579">Emerytura</span><span class="sxs-lookup"><span data-stu-id="784c4-579">Pension</span></span>                        | <span data-ttu-id="784c4-580">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-580">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-581">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="784c4-581">TERMINATION</span></span>            | <span data-ttu-id="784c4-582">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="784c4-582">Termination</span></span>                    | <span data-ttu-id="784c4-583">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-583">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-584">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="784c4-584">RETIREMENT</span></span>             | <span data-ttu-id="784c4-585">Emerytura</span><span class="sxs-lookup"><span data-stu-id="784c4-585">Retirement</span></span>                     | <span data-ttu-id="784c4-586">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-586">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-587">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="784c4-587">ABSENTEE</span></span>               | <span data-ttu-id="784c4-588">Absencja</span><span class="sxs-lookup"><span data-stu-id="784c4-588">Absentee</span></span>                       | <span data-ttu-id="784c4-589">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-589">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-590">INNY</span><span class="sxs-lookup"><span data-stu-id="784c4-590">OTHER</span></span>                  | <span data-ttu-id="784c4-591">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="784c4-591">Other Reasons</span></span>                  | <span data-ttu-id="784c4-592">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-592">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-593">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="784c4-593">CLOSURE</span></span>                | <span data-ttu-id="784c4-594">Zaprzestanie działalności przez firmę</span><span class="sxs-lookup"><span data-stu-id="784c4-594">Business Closure</span></span>               | <span data-ttu-id="784c4-595">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-595">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-596">DEATH</span><span class="sxs-lookup"><span data-stu-id="784c4-596">DEATH</span></span>                  | <span data-ttu-id="784c4-597">Śmierć</span><span class="sxs-lookup"><span data-stu-id="784c4-597">Death</span></span>                          | <span data-ttu-id="784c4-598">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-598">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-599">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="784c4-599">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="784c4-600">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="784c4-600">Leave of Absence</span></span>               | <span data-ttu-id="784c4-601">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-601">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-602">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="784c4-602">CONTRACTEND</span></span>            | <span data-ttu-id="784c4-603">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="784c4-603">End of Contract</span></span>                | <span data-ttu-id="784c4-604">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="784c4-604">Terminate worker</span></span>     |
| <span data-ttu-id="784c4-605">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="784c4-605">SALARYCHANGE</span></span>           | <span data-ttu-id="784c4-606">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="784c4-606">Change of Salary</span></span>               | <span data-ttu-id="784c4-607">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="784c4-607">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="784c4-608">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-608">Terms of employment</span></span>

<span data-ttu-id="784c4-609">Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="784c4-609">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="784c4-610">Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="784c4-610">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="784c4-611">Następujące warunki zatrudnienia i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="784c4-611">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="784c4-612">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="784c4-612">Terms of employment</span></span>   | <span data-ttu-id="784c4-613">opis</span><span class="sxs-lookup"><span data-stu-id="784c4-613">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="784c4-614">Normalna</span><span class="sxs-lookup"><span data-stu-id="784c4-614">Regular</span></span>               | <span data-ttu-id="784c4-615">Normalna</span><span class="sxs-lookup"><span data-stu-id="784c4-615">Regular</span></span>     |
| <span data-ttu-id="784c4-616">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="784c4-616">Direct</span></span>                | <span data-ttu-id="784c4-617">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="784c4-617">Direct</span></span>      |
| <span data-ttu-id="784c4-618">Staż</span><span class="sxs-lookup"><span data-stu-id="784c4-618">Internship</span></span>            | <span data-ttu-id="784c4-619">Staż</span><span class="sxs-lookup"><span data-stu-id="784c4-619">Internship</span></span>  |
| <span data-ttu-id="784c4-620">Stałe</span><span class="sxs-lookup"><span data-stu-id="784c4-620">Permanent</span></span>             | <span data-ttu-id="784c4-621">Stałe</span><span class="sxs-lookup"><span data-stu-id="784c4-621">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="784c4-622">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="784c4-622">Marital status</span></span>

<span data-ttu-id="784c4-623">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-623">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="784c4-624">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-624">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="784c4-625">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-625">Human Resources</span></span>                 | <span data-ttu-id="784c4-626">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-626">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="784c4-627">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="784c4-627">Married</span></span>                | <span data-ttu-id="784c4-628">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="784c4-628">Married</span></span>                   |
| <span data-ttu-id="784c4-629">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="784c4-629">Single</span></span>                 | <span data-ttu-id="784c4-630">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="784c4-630">Single</span></span>                    |
| <span data-ttu-id="784c4-631">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="784c4-631">Widowed</span></span>                | <span data-ttu-id="784c4-632">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="784c4-632">Widowed</span></span>                   |
| <span data-ttu-id="784c4-633">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="784c4-633">Divorced</span></span>               | <span data-ttu-id="784c4-634">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="784c4-634">Divorced</span></span>                  |
| <span data-ttu-id="784c4-635">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="784c4-635">Registered Partnership</span></span> | <span data-ttu-id="784c4-636">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="784c4-636">Domestic Partnership</span></span>      |
| <span data-ttu-id="784c4-637">None</span><span class="sxs-lookup"><span data-stu-id="784c4-637">None</span></span>                   | <span data-ttu-id="784c4-638">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-638">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="784c4-639">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="784c4-639">Cohabiting</span></span>             | <span data-ttu-id="784c4-640">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-640">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="784c4-641">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="784c4-641">Gender</span></span>

<span data-ttu-id="784c4-642">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-642">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="784c4-643">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-643">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="784c4-644">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-644">Human Resources</span></span>       | <span data-ttu-id="784c4-645">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-645">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="784c4-646">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="784c4-646">Male</span></span>         | <span data-ttu-id="784c4-647">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="784c4-647">Male</span></span>                      |
| <span data-ttu-id="784c4-648">Kobieta</span><span class="sxs-lookup"><span data-stu-id="784c4-648">Female</span></span>       | <span data-ttu-id="784c4-649">Kobieta</span><span class="sxs-lookup"><span data-stu-id="784c4-649">Female</span></span>                    |
| <span data-ttu-id="784c4-650">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="784c4-650">Non-specific</span></span> | <span data-ttu-id="784c4-651">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-651">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="784c4-652">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="784c4-652">Payment method</span></span>

<span data-ttu-id="784c4-653">Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę.</span><span class="sxs-lookup"><span data-stu-id="784c4-653">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="784c4-654">Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-654">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="784c4-655">W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-655">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="784c4-656">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-656">Human Resources</span></span>             | <span data-ttu-id="784c4-657">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-657">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="784c4-658">Kasa</span><span class="sxs-lookup"><span data-stu-id="784c4-658">Cash</span></span>               | <span data-ttu-id="784c4-659">Kasa</span><span class="sxs-lookup"><span data-stu-id="784c4-659">Cash</span></span>                      |
| <span data-ttu-id="784c4-660">Płatność elektroniczna</span><span class="sxs-lookup"><span data-stu-id="784c4-660">Electronic Payment</span></span> | <span data-ttu-id="784c4-661">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="784c4-661">Transfer</span></span>                  |
| <span data-ttu-id="784c4-662">Sprawdzanie</span><span class="sxs-lookup"><span data-stu-id="784c4-662">Check</span></span>              | <span data-ttu-id="784c4-663">Czek</span><span class="sxs-lookup"><span data-stu-id="784c4-663">Cheque</span></span>                    |
| <span data-ttu-id="784c4-664">Przekaz bankowy</span><span class="sxs-lookup"><span data-stu-id="784c4-664">Bank Draft</span></span>         | <span data-ttu-id="784c4-665">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-665">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="784c4-666">Inna</span><span class="sxs-lookup"><span data-stu-id="784c4-666">Other</span></span>              | <span data-ttu-id="784c4-667">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-667">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="784c4-668">Typ konta bankowego</span><span class="sxs-lookup"><span data-stu-id="784c4-668">Bank account type</span></span>

<span data-ttu-id="784c4-669">Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="784c4-669">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="784c4-670">Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów.</span><span class="sxs-lookup"><span data-stu-id="784c4-670">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="784c4-671">Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="784c4-671">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="784c4-672">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-672">Human Resources</span></span>            | <span data-ttu-id="784c4-673">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-673">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="784c4-674">Konto czekowe</span><span class="sxs-lookup"><span data-stu-id="784c4-674">Checking Account</span></span>  | <span data-ttu-id="784c4-675">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="784c4-675">CheckingAccount</span></span>           |
| <span data-ttu-id="784c4-676">Konto listy płac</span><span class="sxs-lookup"><span data-stu-id="784c4-676">Payroll Account</span></span>   | <span data-ttu-id="784c4-677">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="784c4-677">PayrollAccount</span></span>            |
| <span data-ttu-id="784c4-678">Konto oszczędnościowe</span><span class="sxs-lookup"><span data-stu-id="784c4-678">Savings Account</span></span>   | <span data-ttu-id="784c4-679">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-679">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="784c4-680">Konto BankGirot</span><span class="sxs-lookup"><span data-stu-id="784c4-680">BankGirot account</span></span> | <span data-ttu-id="784c4-681">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-681">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="784c4-682">Konto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="784c4-682">PlusGirot account</span></span> | <span data-ttu-id="784c4-683">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="784c4-683">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="784c4-684">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="784c4-684">Earning codes</span></span>

<span data-ttu-id="784c4-685">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="784c4-685">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="784c4-686">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="784c4-686">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="784c4-687">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="784c4-687">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="784c4-688">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="784c4-688">Supported frequencies</span></span>

- <span data-ttu-id="784c4-689">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="784c4-689">All</span></span>
- <span data-ttu-id="784c4-690">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="784c4-690">EVERYPAY</span></span>
- <span data-ttu-id="784c4-691">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="784c4-691">EACHPAYPERIOD</span></span>
- <span data-ttu-id="784c4-692">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="784c4-692">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="784c4-693">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="784c4-693">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="784c4-694">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-694">1OFMTH</span></span>
- <span data-ttu-id="784c4-695">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-695">LASTOFMTH</span></span>
- <span data-ttu-id="784c4-696">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-696">2OFMTH</span></span>
- <span data-ttu-id="784c4-697">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-697">3OFMTH</span></span>
- <span data-ttu-id="784c4-698">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-698">4OFMTH</span></span>
- <span data-ttu-id="784c4-699">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-699">5OFMTH</span></span>
- <span data-ttu-id="784c4-700">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-700">1N2OFMTH</span></span>
- <span data-ttu-id="784c4-701">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-701">3N4OFMTH</span></span>
- <span data-ttu-id="784c4-702">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-702">1N3OFMTH</span></span>
- <span data-ttu-id="784c4-703">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-703">1N4OFMTH</span></span>
- <span data-ttu-id="784c4-704">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-704">2N3OFMTH</span></span>
- <span data-ttu-id="784c4-705">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-705">2N4OFMTH</span></span>
- <span data-ttu-id="784c4-706">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-706">1N2N3OFMTH</span></span>
- <span data-ttu-id="784c4-707">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-707">1N2N4OFMTH</span></span>
- <span data-ttu-id="784c4-708">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-708">1N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-709">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-709">2N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-710">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="784c4-710">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="784c4-711">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="784c4-711">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="784c4-712">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-712">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="784c4-713">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-713">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="784c4-714">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="784c4-714">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="784c4-715">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-715">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="784c4-716">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-716">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="784c4-717">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="784c4-717">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="784c4-718">Adresy</span><span class="sxs-lookup"><span data-stu-id="784c4-718">Addresses</span></span>

<span data-ttu-id="784c4-719">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="784c4-719">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="784c4-720">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="784c4-720">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="784c4-721">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="784c4-721">Human Resources</span></span>              | <span data-ttu-id="784c4-722">Dayforce</span><span class="sxs-lookup"><span data-stu-id="784c4-722">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="784c4-723">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="784c4-723">Country/Region</span></span>      | <span data-ttu-id="784c4-724">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="784c4-724">Country Code</span></span>          |
| <span data-ttu-id="784c4-725">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="784c4-725">Zip/Postal Code</span></span>     | <span data-ttu-id="784c4-726">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="784c4-726">Postal Code</span></span>           |
| <span data-ttu-id="784c4-727">Stanowy</span><span class="sxs-lookup"><span data-stu-id="784c4-727">State</span></span>               | <span data-ttu-id="784c4-728">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="784c4-728">State Code</span></span>            |
| <span data-ttu-id="784c4-729">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="784c4-729">City</span></span>                | <span data-ttu-id="784c4-730">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="784c4-730">City</span></span>                  |
| <span data-ttu-id="784c4-731">Powiat</span><span class="sxs-lookup"><span data-stu-id="784c4-731">County</span></span>              | <span data-ttu-id="784c4-732">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="784c4-732">County (Municipality)</span></span> |
| <span data-ttu-id="784c4-733">Ulica</span><span class="sxs-lookup"><span data-stu-id="784c4-733">Street</span></span>              | <span data-ttu-id="784c4-734">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="784c4-734">Address Line 1</span></span>        |
| <span data-ttu-id="784c4-735">Numer budynku</span><span class="sxs-lookup"><span data-stu-id="784c4-735">Street Number</span></span>       | <span data-ttu-id="784c4-736">Wiersz adresu 2</span><span class="sxs-lookup"><span data-stu-id="784c4-736">Address Line 2</span></span>        |
| <span data-ttu-id="784c4-737">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="784c4-737">Building Complement</span></span> | <span data-ttu-id="784c4-738">Wiersz adresu 5</span><span class="sxs-lookup"><span data-stu-id="784c4-738">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="784c4-739">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="784c4-739">Passport number</span></span>

<span data-ttu-id="784c4-740">Pracownicy mogą podać informacje z paszportów.</span><span class="sxs-lookup"><span data-stu-id="784c4-740">Employees can declare passport information.</span></span> <span data-ttu-id="784c4-741">Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="784c4-741">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="784c4-742">Typ identyfikacji = „Paszport”</span><span class="sxs-lookup"><span data-stu-id="784c4-742">Identification Type = "Passport"</span></span>
- <span data-ttu-id="784c4-743">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="784c4-743">Issued Date</span></span>
- <span data-ttu-id="784c4-744">Data ważności</span><span class="sxs-lookup"><span data-stu-id="784c4-744">Expiration Date</span></span>

<span data-ttu-id="784c4-745">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**.</span><span class="sxs-lookup"><span data-stu-id="784c4-745">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="784c4-746">Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce.</span><span class="sxs-lookup"><span data-stu-id="784c4-746">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="784c4-747">Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.</span><span class="sxs-lookup"><span data-stu-id="784c4-747">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>

