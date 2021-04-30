---
title: Konfigurowanie integracji z rozwiązaniem Dayforce
description: Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule. Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PersonnelIntegrationConfiguration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1647b7fbf84a78051e745e918954df32a2e7e1dd
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890011"
---
# <a name="configure-integration-with-dayforce"></a><span data-ttu-id="95ca2-104">Konfigurowanie integracji z rozwiązaniem Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-104">Configure integration with Dayforce</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="95ca2-105">Integracja między programami Microsoft Dynamics 365 Human Resources i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="95ca2-105">The integration between Microsoft Dynamics 365 Human Resources and Ceridian Dayforce relies on several configuration steps that are described in this article.</span></span> <span data-ttu-id="95ca2-106">Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Human Resources i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-106">You must configure the integration in both Human Resources and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="95ca2-107">Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95ca2-107">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Human Resources.</span></span> <span data-ttu-id="95ca2-108">Integracja wymaga określonych danych z programu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95ca2-108">The integration requires specific data from Human Resources.</span></span> <span data-ttu-id="95ca2-109">W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Human Resources w sposób zapewniający obsługę integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-109">Therefore, you must verify that data that is mapped to Dayforce is configured in Human Resources in a manner that supports the integration.</span></span> <span data-ttu-id="95ca2-110">Integracja wykorzystuje następujące ogólne kategorie danych:</span><span class="sxs-lookup"><span data-stu-id="95ca2-110">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="95ca2-111">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-111">Human resources data</span></span>
- <span data-ttu-id="95ca2-112">Dane o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="95ca2-112">Compensation data</span></span>
- <span data-ttu-id="95ca2-113">Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-113">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="95ca2-114">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="95ca2-114">Worker data</span></span>

<span data-ttu-id="95ca2-115">W tym artykule opisano czynności, które należy wykonać, aby włączyć integrację.</span><span class="sxs-lookup"><span data-stu-id="95ca2-115">This article describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="95ca2-116">Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.</span><span class="sxs-lookup"><span data-stu-id="95ca2-116">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="95ca2-117">Włączanie integracji</span><span class="sxs-lookup"><span data-stu-id="95ca2-117">Enable the integration</span></span>

<span data-ttu-id="95ca2-118">W aplikacji Human Resources należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-118">In Human Resources, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="95ca2-119">Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do usługi Microsoft Dynamics 365 Finance, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="95ca2-119">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="95ca2-120">Aby włączyć integrację w aplikacji Human Resources, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="95ca2-120">To turn on the integration in Human Resources, follow these steps.</span></span>

1. <span data-ttu-id="95ca2-121">Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-121">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="95ca2-122">Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="95ca2-122">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="95ca2-123">Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="95ca2-123">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="95ca2-124">Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-124">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="95ca2-125">Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="95ca2-125">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="95ca2-126">W razie potrzeby można zmienić tę częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="95ca2-126">You can change this frequency as you require.</span></span>

<span data-ttu-id="95ca2-127">Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące artykuły poświęcone usłudze Azure:</span><span class="sxs-lookup"><span data-stu-id="95ca2-127">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure articles:</span></span>

- [<span data-ttu-id="95ca2-128">Konta magazynu w usłudze Azure — informacje</span><span class="sxs-lookup"><span data-stu-id="95ca2-128">About Azure storage accounts</span></span>](/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="95ca2-129">Konfigurowanie ciągów połączeń z usługą Azure Storage</span><span class="sxs-lookup"><span data-stu-id="95ca2-129">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="95ca2-130">Dane techniczne, gdy integracja listy płac jest włączona</span><span class="sxs-lookup"><span data-stu-id="95ca2-130">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="95ca2-131">Włączenie integracji listy płac ma dwa główne skutki:</span><span class="sxs-lookup"><span data-stu-id="95ca2-131">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="95ca2-132">Zostanie utworzony projekt eksportu danych o nazwie „Eksport integracji list płac”.</span><span class="sxs-lookup"><span data-stu-id="95ca2-132">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="95ca2-133">Ten projekt zawiera podmioty i pola wymagane do integracji listy płac.</span><span class="sxs-lookup"><span data-stu-id="95ca2-133">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="95ca2-134">Aby sprawdzić projekt, przejdź do **Administracja systemu**, wybierz kafelek **Zarządzanie danymi**, a następnie otwórz projekt danych z listy projektów.</span><span class="sxs-lookup"><span data-stu-id="95ca2-134">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="95ca2-135">To zadanie wsadowe wykonuje projekt eksportu danych, szyfruje otrzymany pakiet danych i przesyła plik pakietu danych do punktu końcowego SFTP skonfigurowanego na ekranie **Integracja konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-135">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="95ca2-136">Pakiet danych przesłany do punktu końcowego SFTP jest szyfrowany przy użyciu klucza unikalnego dla pakietu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-136">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="95ca2-137">Klucz to Azure Key Vault dostępny jedynie przez Ceridian.</span><span class="sxs-lookup"><span data-stu-id="95ca2-137">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="95ca2-138">Nie jest możliwe odszyfrowanie i sprawdzenie zawartości pakietu danych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-138">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="95ca2-139">Jeśli chcesz sprawdzić zawartość pakietu danych, musisz ręcznie wyeksportować projekt danych „Eksportu integracji płac”, pobrać go, a następnie otworzyć.</span><span class="sxs-lookup"><span data-stu-id="95ca2-139">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="95ca2-140">Ręczny eksport nie zastosuje szyfrowania ani nie dokona transferu pakietu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-140">Manual export will not apply encryption or transfer the package.</span></span>
> <span data-ttu-id="95ca2-141">W przypadkach, w których pliki integracji są wysyłane ze środowiska Dynamics 365 Human Resources UAT lub Sandbox do środowiska Ceridian Dayforce Test, możesz użyć następującego adresu URL magazynu kluczy: https://payrollintegrationprod.vault.azure.net</span><span class="sxs-lookup"><span data-stu-id="95ca2-141">For instances where the integration files are sent from a Dynamics 365 Human Resources UAT or Sandbox environment to a Ceridian Dayforce Test environment, you can use the following key vault URL: https://payrollintegrationprod.vault.azure.net.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="95ca2-142">Konfigurowanie danych</span><span class="sxs-lookup"><span data-stu-id="95ca2-142">Configure your data</span></span> 

<span data-ttu-id="95ca2-143">Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95ca2-143">To process payroll, you must configure human resource data in Human Resources.</span></span> <span data-ttu-id="95ca2-144">Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="95ca2-144">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="95ca2-145">Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-145">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="95ca2-146">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-146">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="95ca2-147">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-147">Benefits</span></span> 

<span data-ttu-id="95ca2-148">Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-148">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="95ca2-149">Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-149">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="95ca2-150">Plany świadczeń</span><span class="sxs-lookup"><span data-stu-id="95ca2-150">Benefit plans</span></span>

- <span data-ttu-id="95ca2-151">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-151">Plan (required)</span></span>
- <span data-ttu-id="95ca2-152">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-152">Type (required)</span></span>
- <span data-ttu-id="95ca2-153">Wpływ na listę płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-153">Payroll impact (required)</span></span>
- <span data-ttu-id="95ca2-154">Odzyskaj zaległości</span><span class="sxs-lookup"><span data-stu-id="95ca2-154">Recover arrears</span></span>
- <span data-ttu-id="95ca2-155">Metoda potrącenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-155">Deduction method</span></span>
- <span data-ttu-id="95ca2-156">Priorytet potrącenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-156">Deduction priority</span></span>
- <span data-ttu-id="95ca2-157">Okres limitu</span><span class="sxs-lookup"><span data-stu-id="95ca2-157">Limit period</span></span>
- <span data-ttu-id="95ca2-158">Kwota limitu</span><span class="sxs-lookup"><span data-stu-id="95ca2-158">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="95ca2-159">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-159">Benefits</span></span>

- <span data-ttu-id="95ca2-160">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-160">Plan (required)</span></span>
- <span data-ttu-id="95ca2-161">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-161">Type (required)</span></span>
- <span data-ttu-id="95ca2-162">Opcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-162">Option (required)</span></span>
- <span data-ttu-id="95ca2-163">Identyfikator świadczenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-163">Benefit ID (required)</span></span>
- <span data-ttu-id="95ca2-164">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="95ca2-164">Frequency</span></span>
- <span data-ttu-id="95ca2-165">Podstawa</span><span class="sxs-lookup"><span data-stu-id="95ca2-165">Basis</span></span>
- <span data-ttu-id="95ca2-166">Kwota lub stawka</span><span class="sxs-lookup"><span data-stu-id="95ca2-166">Amount or rate</span></span>
- <span data-ttu-id="95ca2-167">Kod zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-167">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="95ca2-168">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="95ca2-168">Supported frequencies</span></span> 

- <span data-ttu-id="95ca2-169">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="95ca2-169">Weekly</span></span>
- <span data-ttu-id="95ca2-170">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="95ca2-170">Bi-weekly</span></span>
- <span data-ttu-id="95ca2-171">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="95ca2-171">Semi-monthly</span></span>
- <span data-ttu-id="95ca2-172">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="95ca2-172">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="95ca2-173">Obsługiwane podstawy</span><span class="sxs-lookup"><span data-stu-id="95ca2-173">Supported bases</span></span> 

- <span data-ttu-id="95ca2-174">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="95ca2-174">Fixed amount</span></span>
- <span data-ttu-id="95ca2-175">Procent zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-175">Percent of earnings</span></span>
- <span data-ttu-id="95ca2-176">Godziny płatne</span><span class="sxs-lookup"><span data-stu-id="95ca2-176">Productive hours</span></span>

<span data-ttu-id="95ca2-177">System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="95ca2-177">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="95ca2-178">Przeglądanie zadań w Human Resources</span><span class="sxs-lookup"><span data-stu-id="95ca2-178">Selection in Human Resources</span></span>        | <span data-ttu-id="95ca2-179">Wynik w systemie Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-179">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="95ca2-180">Brak</span><span class="sxs-lookup"><span data-stu-id="95ca2-180">None</span></span>                       | <span data-ttu-id="95ca2-181">Nie jest tworzone żadne potrącenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-181">No deduction is created.</span></span>                      |
| <span data-ttu-id="95ca2-182">Tylko potrącenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-182">Deduction only</span></span>             | <span data-ttu-id="95ca2-183">Jest tworzone potrącenie od pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-183">An employee deduction is created.</span></span>             |
| <span data-ttu-id="95ca2-184">Tylko udział</span><span class="sxs-lookup"><span data-stu-id="95ca2-184">Contribution only</span></span>          | <span data-ttu-id="95ca2-185">Jest tworzone potrącenie od pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-185">An employer deduction is created.</span></span>             |
| <span data-ttu-id="95ca2-186">Potrącenie i udział</span><span class="sxs-lookup"><span data-stu-id="95ca2-186">Deduction and contribution</span></span> | <span data-ttu-id="95ca2-187">Są tworzone potrącenia od pracownika i pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-187">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="95ca2-188">Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="95ca2-188">For more information about how to define and manage a benefits program, see the following articles:</span></span>

- [<span data-ttu-id="95ca2-189">Dostarczanie programu świadczeń dla pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="95ca2-189">Deliver an employee benefits program</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="95ca2-190">Utwórz nowe świadczenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-190">Create a new benefit</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="95ca2-191">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-191">Define benefit eligibility rules and policies</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="95ca2-192">Rejestrowanie i usuwanie świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="95ca2-192">Enroll and remove benefits from workers</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="95ca2-193">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-193">Compensation</span></span> 

<span data-ttu-id="95ca2-194">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="95ca2-194">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="95ca2-195">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="95ca2-195">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="95ca2-196">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="95ca2-196">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="95ca2-197">Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-197">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="95ca2-198">Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-198">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="95ca2-199">Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="95ca2-199">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="95ca2-200">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="95ca2-200">For more information about compensation plans, see the following articles:</span></span>

- [<span data-ttu-id="95ca2-201">Tworzenie planów stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="95ca2-201">Create fixed compensation plans</span></span>](/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="95ca2-202">Tworzenie planów wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="95ca2-202">Create variable compensation plans</span></span>](/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="95ca2-203">Opracowywanie struktury i planu pensji/wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="95ca2-203">Develop salary/compensation structure and plans</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="95ca2-204">Przetwarzanie wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-204">Process compensation</span></span>](/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="95ca2-205">Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników</span><span class="sxs-lookup"><span data-stu-id="95ca2-205">Define compensation process and calculate results</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="95ca2-206">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="95ca2-206">Enroll an employee in a fixed compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="95ca2-207">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="95ca2-207">Enroll an employee in a variable compensation plan</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="95ca2-208">Funkcje</span><span class="sxs-lookup"><span data-stu-id="95ca2-208">Jobs</span></span> 

<span data-ttu-id="95ca2-209">Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję.</span><span class="sxs-lookup"><span data-stu-id="95ca2-209">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="95ca2-210">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="95ca2-210">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95ca2-211">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="95ca2-211">Setting up the components of a job</span></span>](/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="95ca2-212">Definiowanie nowych funkcji</span><span class="sxs-lookup"><span data-stu-id="95ca2-212">Define new jobs</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="95ca2-213">Pozycje</span><span class="sxs-lookup"><span data-stu-id="95ca2-213">Positions</span></span>

<span data-ttu-id="95ca2-214">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="95ca2-214">A position is an individual instance of a job.</span></span> <span data-ttu-id="95ca2-215">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="95ca2-215">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="95ca2-216">Stanowisko istnieje w dziale.</span><span class="sxs-lookup"><span data-stu-id="95ca2-216">A position exists in a department.</span></span> <span data-ttu-id="95ca2-217">Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="95ca2-217">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="95ca2-218">Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="95ca2-218">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="95ca2-219">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-219">Position (required)</span></span>
- <span data-ttu-id="95ca2-220">Opis (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-220">Description (required)</span></span>
- <span data-ttu-id="95ca2-221">Funkcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-221">Job (required)</span></span>
- <span data-ttu-id="95ca2-222">Dział (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-222">Department (required)</span></span>
- <span data-ttu-id="95ca2-223">Typ stanowiska (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-223">Position type (required)</span></span>
- <span data-ttu-id="95ca2-224">W przeliczeniu na pełne etaty</span><span class="sxs-lookup"><span data-stu-id="95ca2-224">Full-time equivalent</span></span>
- <span data-ttu-id="95ca2-225">Zwykłe godziny (rocznie) (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-225">Annual regular hours (required)</span></span>
- <span data-ttu-id="95ca2-226">Zapłacone przez firmę (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-226">Paid by legal entity (required)</span></span>
- <span data-ttu-id="95ca2-227">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-227">Pay cycle (required)</span></span>
- <span data-ttu-id="95ca2-228">Domyślny wymiar finansowy — Centrum kosztu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-228">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="95ca2-229">Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="95ca2-229">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="95ca2-230">Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-230">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="95ca2-231">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="95ca2-231">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95ca2-232">Organizowanie pracowników za pomocą działów, funkcji i stanowisk</span><span class="sxs-lookup"><span data-stu-id="95ca2-232">Organize your workforce using departments, jobs, and positions</span></span>](/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="95ca2-233">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="95ca2-233">Set up positions</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="95ca2-234">Działy</span><span class="sxs-lookup"><span data-stu-id="95ca2-234">Departments</span></span>

<span data-ttu-id="95ca2-235">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-235">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="95ca2-236">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="95ca2-236">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="95ca2-237">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-237">You can use departments to report on functional areas.</span></span> <span data-ttu-id="95ca2-238">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="95ca2-238">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="95ca2-239">Aby uzyskać więcej informacji, zobacz następujące artykuły:</span><span class="sxs-lookup"><span data-stu-id="95ca2-239">For more information, see the following articles:</span></span>

- [<span data-ttu-id="95ca2-240">Tworzenie działu i kojarzenie go z hierarchią działów</span><span class="sxs-lookup"><span data-stu-id="95ca2-240">Create a department and associate it with the department hierarchy</span></span>](/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="95ca2-241">Definiowanie nowych działów</span><span class="sxs-lookup"><span data-stu-id="95ca2-241">Define new departments</span></span>](/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="95ca2-242">Cykle płac i okresy płac</span><span class="sxs-lookup"><span data-stu-id="95ca2-242">Pay cycles and pay periods</span></span>

<span data-ttu-id="95ca2-243">Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="95ca2-243">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="95ca2-244">Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="95ca2-244">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="95ca2-245">Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="95ca2-245">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="95ca2-246">Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="95ca2-246">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="95ca2-247">Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-247">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="95ca2-248">Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach.</span><span class="sxs-lookup"><span data-stu-id="95ca2-248">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="95ca2-249">Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-249">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="95ca2-250">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="95ca2-250">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="95ca2-251">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-251">Pay cycle (required)</span></span>
- <span data-ttu-id="95ca2-252">Częstotliwość cyklu kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-252">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="95ca2-253">Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="95ca2-253">Period start date (first pay period required)</span></span>
- <span data-ttu-id="95ca2-254">Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="95ca2-254">Default payment date (first pay period required)</span></span>

<span data-ttu-id="95ca2-255">Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="95ca2-255">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="95ca2-256">Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="95ca2-256">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="95ca2-257">System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Human Resources.</span><span class="sxs-lookup"><span data-stu-id="95ca2-257">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Human Resources.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="95ca2-258">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-258">Earning codes</span></span>

<span data-ttu-id="95ca2-259">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-259">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95ca2-260">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="95ca2-260">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="95ca2-261">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="95ca2-261">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="95ca2-262">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-262">Earning Code (required)</span></span>
- <span data-ttu-id="95ca2-263">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-263">Description</span></span>
- <span data-ttu-id="95ca2-264">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="95ca2-264">Unit of measure</span></span>
- <span data-ttu-id="95ca2-265">Płatne</span><span class="sxs-lookup"><span data-stu-id="95ca2-265">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="95ca2-266">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="95ca2-266">Worker data</span></span>

<span data-ttu-id="95ca2-267">Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-267">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="95ca2-268">Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-268">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="95ca2-269">Można przechowywać następujące informacje o pracownikach:</span><span class="sxs-lookup"><span data-stu-id="95ca2-269">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="95ca2-270">**Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.</span><span class="sxs-lookup"><span data-stu-id="95ca2-270">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="95ca2-271">**Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-271">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="95ca2-272">**Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.</span><span class="sxs-lookup"><span data-stu-id="95ca2-272">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="95ca2-273">**Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-273">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="95ca2-274">Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-274">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="95ca2-275">Informacje ogólne</span><span class="sxs-lookup"><span data-stu-id="95ca2-275">General information</span></span>

- <span data-ttu-id="95ca2-276">Numer pracownika (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-276">Personnel number (required)</span></span>
- <span data-ttu-id="95ca2-277">Imię (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-277">First name (required)</span></span>
- <span data-ttu-id="95ca2-278">Nazwisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-278">Last name (required)</span></span>
- <span data-ttu-id="95ca2-279">Drugie imię</span><span class="sxs-lookup"><span data-stu-id="95ca2-279">Middle name</span></span>
- <span data-ttu-id="95ca2-280">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="95ca2-280">Seniority date</span></span>
- <span data-ttu-id="95ca2-281">Znane jako</span><span class="sxs-lookup"><span data-stu-id="95ca2-281">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="95ca2-282">Informacje osobiste</span><span class="sxs-lookup"><span data-stu-id="95ca2-282">Personal information</span></span>

- <span data-ttu-id="95ca2-283">Stan cywilny (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-283">Marital status (required)</span></span>
- <span data-ttu-id="95ca2-284">Data urodzenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-284">Birth date (required)</span></span>
- <span data-ttu-id="95ca2-285">Płeć (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-285">Gender (required)</span></span>
- <span data-ttu-id="95ca2-286">Osoba niepełnosprawna</span><span class="sxs-lookup"><span data-stu-id="95ca2-286">Person with disabilities</span></span>
- <span data-ttu-id="95ca2-287">Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="95ca2-287">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="95ca2-288">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-288">Address information</span></span>

- <span data-ttu-id="95ca2-289">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-289">Primary (required)</span></span>
- <span data-ttu-id="95ca2-290">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-290">Country/region (required)</span></span>
- <span data-ttu-id="95ca2-291">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-291">Postal code (required)</span></span>
- <span data-ttu-id="95ca2-292">Numer domu (wymagane) (jedynie w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="95ca2-292">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="95ca2-293">Dodatkowe określenie budynku (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="95ca2-293">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="95ca2-294">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-294">City (required)</span></span>
- <span data-ttu-id="95ca2-295">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-295">State (required)</span></span>
- <span data-ttu-id="95ca2-296">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-296">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="95ca2-297">Informacje o kontakcie</span><span class="sxs-lookup"><span data-stu-id="95ca2-297">Contact information</span></span> 

- <span data-ttu-id="95ca2-298">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-298">Primary (required)</span></span>
- <span data-ttu-id="95ca2-299">Nazwa osoby kontaktowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-299">Contact number (required)</span></span>
- <span data-ttu-id="95ca2-300">Wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="95ca2-300">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="95ca2-301">Informacje płacowe i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-301">Payroll information and earning codes</span></span>

<span data-ttu-id="95ca2-302">Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="95ca2-302">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="95ca2-303">Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-303">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="95ca2-304">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-304">Earning codes</span></span>

- <span data-ttu-id="95ca2-305">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-305">Position (required)</span></span>
- <span data-ttu-id="95ca2-306">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-306">Earning Code (required)</span></span>
- <span data-ttu-id="95ca2-307">Częstotliwość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-307">Frequency (required)</span></span>
- <span data-ttu-id="95ca2-308">Kwota (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-308">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="95ca2-309">Informacje listy płac</span><span class="sxs-lookup"><span data-stu-id="95ca2-309">Payroll information</span></span>

- <span data-ttu-id="95ca2-310">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="95ca2-310">Payment Method</span></span>
- <span data-ttu-id="95ca2-311">Region gospodarczy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-311">Economic Region (required)</span></span>
- <span data-ttu-id="95ca2-312">Identyfikator świadczeń pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="95ca2-312">Employee Benefits ID</span></span>
- <span data-ttu-id="95ca2-313">Numer dowodu osobistego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-313">National ID Number (required)</span></span>
- <span data-ttu-id="95ca2-314">Numer książeczki wojskowej</span><span class="sxs-lookup"><span data-stu-id="95ca2-314">Military Service Number</span></span>
- <span data-ttu-id="95ca2-315">Identyfikator zmiany (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-315">Shift ID (required)</span></span>
- <span data-ttu-id="95ca2-316">Numer identyfikacji podatkowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-316">Tax Number (required)</span></span>
- <span data-ttu-id="95ca2-317">Identyfikator związku (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-317">Union ID (required)</span></span>
- <span data-ttu-id="95ca2-318">Identyfikator dnia roboczego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-318">Work Day ID (required)</span></span>
- <span data-ttu-id="95ca2-319">Numer pozwolenia na pracę</span><span class="sxs-lookup"><span data-stu-id="95ca2-319">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="95ca2-320">W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-320">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="95ca2-321">Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-321">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="95ca2-322">Szczegóły zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-322">Employment details</span></span>

<span data-ttu-id="95ca2-323">Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-323">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="95ca2-324">W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.</span><span class="sxs-lookup"><span data-stu-id="95ca2-324">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="95ca2-325">Data rozpoczęcia zatrudnienia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-325">Employment start date (required)</span></span>
- <span data-ttu-id="95ca2-326">Data zakończenia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-326">Employment end date</span></span>
- <span data-ttu-id="95ca2-327">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="95ca2-327">Start date</span></span>
- <span data-ttu-id="95ca2-328">Dopasowana data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-328">Adjusted start date</span></span>
- <span data-ttu-id="95ca2-329">Data zakończenia (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="95ca2-329">Termination date (required upon termination)</span></span>
- <span data-ttu-id="95ca2-330">Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="95ca2-330">Termination reason (required upon termination)</span></span>

<span data-ttu-id="95ca2-331">Kluczowe daty pracownika są obliczane na podstawie następujących informacji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-331">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="95ca2-332">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-332">Human Resources</span></span>                | <span data-ttu-id="95ca2-333">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-333">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="95ca2-334">Ostatnia data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-334">Most recent hire date</span></span> | <span data-ttu-id="95ca2-335">Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-335">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="95ca2-336">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-336">Termination date</span></span>      | <span data-ttu-id="95ca2-337">Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-337">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="95ca2-338">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="95ca2-338">Start date</span></span>            | <span data-ttu-id="95ca2-339">Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-339">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="95ca2-340">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-340">Original hire date</span></span>    | <span data-ttu-id="95ca2-341">Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-341">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="95ca2-342">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-342">Compensation</span></span>

<span data-ttu-id="95ca2-343">Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-343">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="95ca2-344">Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-344">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="95ca2-345">Data obowiązywania (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-345">Effective Date (required)</span></span>
- <span data-ttu-id="95ca2-346">Data ważności</span><span class="sxs-lookup"><span data-stu-id="95ca2-346">Expiration date</span></span>
- <span data-ttu-id="95ca2-347">Stawka płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-347">Pay Rate (required)</span></span>
- <span data-ttu-id="95ca2-348">Konwersje stawek płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-348">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="95ca2-349">Równowartość roczna (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-349">Annual equivalent (required)</span></span>
- <span data-ttu-id="95ca2-350">Równowartość godzinowa (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-350">Hourly equivalent (required)</span></span>

<span data-ttu-id="95ca2-351">Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-351">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="95ca2-352">Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-352">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="95ca2-353">Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-353">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="95ca2-354">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="95ca2-354">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="95ca2-355">Numer ubezpieczenia społecznego</span><span class="sxs-lookup"><span data-stu-id="95ca2-355">Social Security identifier</span></span> 

<span data-ttu-id="95ca2-356">Każdy pracownik musi mieć jeden identyfikator podstawowy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-356">Every employee must have one primary identifier.</span></span> <span data-ttu-id="95ca2-357">Identyfikator ten musi być typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-357">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="95ca2-358">W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-358">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="95ca2-359">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-359">Primary (required)</span></span>
- <span data-ttu-id="95ca2-360">Typ identyfikacji = „PESEL”</span><span class="sxs-lookup"><span data-stu-id="95ca2-360">Identification Type = "SSN"</span></span>
- <span data-ttu-id="95ca2-361">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-361">Issued Date</span></span>
- <span data-ttu-id="95ca2-362">Data ważności</span><span class="sxs-lookup"><span data-stu-id="95ca2-362">Expiration Date</span></span>

<span data-ttu-id="95ca2-363">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-363">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="95ca2-364">Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.</span><span class="sxs-lookup"><span data-stu-id="95ca2-364">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="95ca2-365">Konta bankowe i wypłaty</span><span class="sxs-lookup"><span data-stu-id="95ca2-365">Bank accounts and disbursements</span></span>

<span data-ttu-id="95ca2-366">Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="95ca2-366">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="95ca2-367">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-367">Human Resources</span></span>                         | <span data-ttu-id="95ca2-368">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-368">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="95ca2-369">Numer konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-369">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="95ca2-370">Kod SWIFT (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-370">SWIFT code (required)</span></span>          | <span data-ttu-id="95ca2-371">Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="95ca2-371">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="95ca2-372">Numer oddziału (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-372">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="95ca2-373">Typ konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-373">Bank account type (required)</span></span>   | <span data-ttu-id="95ca2-374">Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="95ca2-374">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="95ca2-375">Obsługiwane wartości **Czekowe** i **Lista płac**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-375">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="95ca2-376">Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku.</span><span class="sxs-lookup"><span data-stu-id="95ca2-376">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="95ca2-377">Wszystkie inne konta pozostałości są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-377">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="95ca2-378">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-378">Address information</span></span>

<span data-ttu-id="95ca2-379">Każdy pracownik musi mieć jedną lokalizację podstawową.</span><span class="sxs-lookup"><span data-stu-id="95ca2-379">Every employee must have one primary location.</span></span> <span data-ttu-id="95ca2-380">W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-380">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="95ca2-381">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-381">Primary (required)</span></span>
- <span data-ttu-id="95ca2-382">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-382">Country/region (required)</span></span>
- <span data-ttu-id="95ca2-383">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-383">Zip/postal code (required)</span></span>
- <span data-ttu-id="95ca2-384">Ulica (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-384">Street (required)</span></span>
- <span data-ttu-id="95ca2-385">Numer domu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-385">Street Number (required)</span></span>
- <span data-ttu-id="95ca2-386">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="95ca2-386">Building Complement</span></span>
- <span data-ttu-id="95ca2-387">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-387">City (required)</span></span>
- <span data-ttu-id="95ca2-388">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-388">State (required)</span></span>
- <span data-ttu-id="95ca2-389">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-389">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="95ca2-390">Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie</span><span class="sxs-lookup"><span data-stu-id="95ca2-390">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="95ca2-391">Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="95ca2-391">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="95ca2-392">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-392">Departments are required on positions.</span></span>
- <span data-ttu-id="95ca2-393">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-393">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="95ca2-394">Można skonfigurować Human Resources tak, aby Stanowiska umożliwiały określenie działu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-394">You can configure Human Resources to require that Positions specify a Department.</span></span> <span data-ttu-id="95ca2-395">Aby to zrobić, przejdź do **stanowisk udostępnionych zasobów ludzkich > Stanowisk > wymagają działów stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-395">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="95ca2-396">Zaleca się, aby to ustawienie zostało wymuszone dla integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-396">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="95ca2-397">Typy funkcji</span><span class="sxs-lookup"><span data-stu-id="95ca2-397">Job types</span></span>

<span data-ttu-id="95ca2-398">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="95ca2-398">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="95ca2-399">Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie.</span><span class="sxs-lookup"><span data-stu-id="95ca2-399">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="95ca2-400">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="95ca2-400">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="95ca2-401">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-401">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="95ca2-402">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-402">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-403">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="95ca2-403">Job type</span></span>   | <span data-ttu-id="95ca2-404">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-404">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="95ca2-405">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="95ca2-405">Hourly</span></span>     | <span data-ttu-id="95ca2-406">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="95ca2-406">Hourly</span></span>      |
| <span data-ttu-id="95ca2-407">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="95ca2-407">Salaried</span></span>   | <span data-ttu-id="95ca2-408">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="95ca2-408">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="95ca2-409">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="95ca2-409">Position types</span></span> 

<span data-ttu-id="95ca2-410">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="95ca2-410">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="95ca2-411">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-411">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="95ca2-412">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-412">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-413">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="95ca2-413">Position type</span></span>   | <span data-ttu-id="95ca2-414">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-414">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="95ca2-415">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="95ca2-415">Full-time</span></span>       | <span data-ttu-id="95ca2-416">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="95ca2-416">Full time employee</span></span> |
| <span data-ttu-id="95ca2-417">Część etatu</span><span class="sxs-lookup"><span data-stu-id="95ca2-417">Part-time</span></span>       | <span data-ttu-id="95ca2-418">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="95ca2-418">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="95ca2-419">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="95ca2-419">Reason codes</span></span>

<span data-ttu-id="95ca2-420">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-420">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="95ca2-421">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-421">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="95ca2-422">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-422">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-423">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="95ca2-423">Reason code</span></span>    | <span data-ttu-id="95ca2-424">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-424">Description</span></span>      | <span data-ttu-id="95ca2-425">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="95ca2-425">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="95ca2-426">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="95ca2-426">RESIGNATION</span></span>    | <span data-ttu-id="95ca2-427">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="95ca2-427">Resignation</span></span>      | <span data-ttu-id="95ca2-428">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-428">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-429">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="95ca2-429">TERMINATION</span></span>    | <span data-ttu-id="95ca2-430">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="95ca2-430">Termination</span></span>      | <span data-ttu-id="95ca2-431">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-431">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-432">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="95ca2-432">RETIREMENT</span></span>     | <span data-ttu-id="95ca2-433">Emerytura</span><span class="sxs-lookup"><span data-stu-id="95ca2-433">Retirement</span></span>       | <span data-ttu-id="95ca2-434">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-434">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-435">INNY</span><span class="sxs-lookup"><span data-stu-id="95ca2-435">OTHER</span></span>          | <span data-ttu-id="95ca2-436">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="95ca2-436">Other Reasons</span></span>    | <span data-ttu-id="95ca2-437">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-437">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-438">DEATH</span><span class="sxs-lookup"><span data-stu-id="95ca2-438">DEATH</span></span>          | <span data-ttu-id="95ca2-439">Śmierć</span><span class="sxs-lookup"><span data-stu-id="95ca2-439">Death</span></span>            | <span data-ttu-id="95ca2-440">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-440">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-441">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="95ca2-441">LEAVEOFABSENCE</span></span> | <span data-ttu-id="95ca2-442">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="95ca2-442">Leave of Absence</span></span> | <span data-ttu-id="95ca2-443">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-443">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-444">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="95ca2-444">CONTRACTEND</span></span>    | <span data-ttu-id="95ca2-445">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-445">End of Contract</span></span>  | <span data-ttu-id="95ca2-446">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-446">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-447">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="95ca2-447">SALARYCHANGE</span></span>   | <span data-ttu-id="95ca2-448">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-448">Change of Salary</span></span> | <span data-ttu-id="95ca2-449">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-449">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="95ca2-450">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="95ca2-450">Marital status</span></span>

<span data-ttu-id="95ca2-451">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-451">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95ca2-452">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-452">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="95ca2-453">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-453">Human Resources</span></span>                 | <span data-ttu-id="95ca2-454">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-454">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="95ca2-455">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="95ca2-455">Married</span></span>                | <span data-ttu-id="95ca2-456">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="95ca2-456">Married</span></span>              |
| <span data-ttu-id="95ca2-457">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="95ca2-457">Single</span></span>                 | <span data-ttu-id="95ca2-458">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="95ca2-458">Single</span></span>               |
| <span data-ttu-id="95ca2-459">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="95ca2-459">Widowed</span></span>                | <span data-ttu-id="95ca2-460">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="95ca2-460">Widowed</span></span>              |
| <span data-ttu-id="95ca2-461">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="95ca2-461">Divorced</span></span>               | <span data-ttu-id="95ca2-462">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="95ca2-462">Divorced</span></span>             |
| <span data-ttu-id="95ca2-463">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="95ca2-463">Registered Partnership</span></span> | <span data-ttu-id="95ca2-464">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-464">Domestic Partnership</span></span> |
| <span data-ttu-id="95ca2-465">None</span><span class="sxs-lookup"><span data-stu-id="95ca2-465">None</span></span>                   | <span data-ttu-id="95ca2-466">None</span><span class="sxs-lookup"><span data-stu-id="95ca2-466">None</span></span>                 |
| <span data-ttu-id="95ca2-467">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="95ca2-467">Cohabiting</span></span>             | <span data-ttu-id="95ca2-468">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="95ca2-468">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="95ca2-469">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="95ca2-469">Gender</span></span>

<span data-ttu-id="95ca2-470">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-470">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95ca2-471">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-471">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="95ca2-472">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-472">Human Resources</span></span>       | <span data-ttu-id="95ca2-473">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-473">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="95ca2-474">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="95ca2-474">Male</span></span>         | <span data-ttu-id="95ca2-475">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="95ca2-475">Male</span></span>            |
| <span data-ttu-id="95ca2-476">Kobieta</span><span class="sxs-lookup"><span data-stu-id="95ca2-476">Female</span></span>       | <span data-ttu-id="95ca2-477">Kobieta</span><span class="sxs-lookup"><span data-stu-id="95ca2-477">Female</span></span>          |
| <span data-ttu-id="95ca2-478">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="95ca2-478">Non-specific</span></span> | <span data-ttu-id="95ca2-479">*Nieobsługiwane*</span><span class="sxs-lookup"><span data-stu-id="95ca2-479">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="95ca2-480">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-480">Earning codes</span></span>

<span data-ttu-id="95ca2-481">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-481">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95ca2-482">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="95ca2-482">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="95ca2-483">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-483">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="95ca2-484">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="95ca2-484">Supported frequencies</span></span>

- <span data-ttu-id="95ca2-485">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="95ca2-485">All</span></span>
- <span data-ttu-id="95ca2-486">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="95ca2-486">EVERYPAY</span></span>
- <span data-ttu-id="95ca2-487">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="95ca2-487">EACHPAYPERIOD</span></span>
- <span data-ttu-id="95ca2-488">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="95ca2-488">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="95ca2-489">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="95ca2-489">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="95ca2-490">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-490">1OFMTH</span></span>
- <span data-ttu-id="95ca2-491">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-491">LASTOFMTH</span></span>
- <span data-ttu-id="95ca2-492">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-492">2OFMTH</span></span>
- <span data-ttu-id="95ca2-493">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-493">3OFMTH</span></span>
- <span data-ttu-id="95ca2-494">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-494">4OFMTH</span></span>
- <span data-ttu-id="95ca2-495">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-495">5OFMTH</span></span>
- <span data-ttu-id="95ca2-496">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-496">1N2OFMTH</span></span>
- <span data-ttu-id="95ca2-497">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-497">3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-498">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-498">1N3OFMTH</span></span>
- <span data-ttu-id="95ca2-499">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-499">1N4OFMTH</span></span>
- <span data-ttu-id="95ca2-500">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-500">2N3OFMTH</span></span>
- <span data-ttu-id="95ca2-501">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-501">2N4OFMTH</span></span>
- <span data-ttu-id="95ca2-502">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-502">1N2N3OFMTH</span></span>
- <span data-ttu-id="95ca2-503">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-503">1N2N4OFMTH</span></span>
- <span data-ttu-id="95ca2-504">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-504">1N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-505">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-505">2N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-506">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-506">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-507">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="95ca2-507">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="95ca2-508">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-508">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="95ca2-509">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-509">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="95ca2-510">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-510">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="95ca2-511">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-511">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="95ca2-512">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-512">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="95ca2-513">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-513">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="95ca2-514">Adresy</span><span class="sxs-lookup"><span data-stu-id="95ca2-514">Addresses</span></span>

<span data-ttu-id="95ca2-515">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="95ca2-515">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="95ca2-516">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="95ca2-516">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="95ca2-517">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-517">Human Resources</span></span>          | <span data-ttu-id="95ca2-518">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-518">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="95ca2-519">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="95ca2-519">Country/Region</span></span>  | <span data-ttu-id="95ca2-520">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="95ca2-520">Country Code</span></span>          |
| <span data-ttu-id="95ca2-521">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-521">Zip/Postal Code</span></span> | <span data-ttu-id="95ca2-522">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-522">Postal Code</span></span>           |
| <span data-ttu-id="95ca2-523">Stanowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-523">State</span></span>           | <span data-ttu-id="95ca2-524">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="95ca2-524">State Code</span></span>            |
| <span data-ttu-id="95ca2-525">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="95ca2-525">City</span></span>            | <span data-ttu-id="95ca2-526">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="95ca2-526">City</span></span>                  |
| <span data-ttu-id="95ca2-527">Powiat</span><span class="sxs-lookup"><span data-stu-id="95ca2-527">County</span></span>          | <span data-ttu-id="95ca2-528">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="95ca2-528">County (Municipality)</span></span> |
| <span data-ttu-id="95ca2-529">Ulica</span><span class="sxs-lookup"><span data-stu-id="95ca2-529">Street</span></span>          | <span data-ttu-id="95ca2-530">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="95ca2-530">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="95ca2-531">Regiony podatkowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-531">Tax regions</span></span>

<span data-ttu-id="95ca2-532">Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac.</span><span class="sxs-lookup"><span data-stu-id="95ca2-532">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="95ca2-533">Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-533">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="95ca2-534">Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-534">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="95ca2-535">Region podatkowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-535">Tax region (required)</span></span>
- <span data-ttu-id="95ca2-536">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-536">Country/Region (required)</span></span>
- <span data-ttu-id="95ca2-537">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-537">State (required)</span></span>
- <span data-ttu-id="95ca2-538">Powiat</span><span class="sxs-lookup"><span data-stu-id="95ca2-538">County</span></span> 
- <span data-ttu-id="95ca2-539">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="95ca2-539">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="95ca2-540">Konfigurowanie danych w celu generowania listy płac w Meksyku</span><span class="sxs-lookup"><span data-stu-id="95ca2-540">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="95ca2-541">Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="95ca2-541">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="95ca2-542">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-542">Departments are required on positions.</span></span>
- <span data-ttu-id="95ca2-543">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="95ca2-543">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="95ca2-544">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="95ca2-544">Job types</span></span>

<span data-ttu-id="95ca2-545">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="95ca2-545">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="95ca2-546">Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="95ca2-546">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="95ca2-547">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="95ca2-547">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="95ca2-548">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-548">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="95ca2-549">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-549">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-550">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="95ca2-550">Job type</span></span>   | <span data-ttu-id="95ca2-551">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-551">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="95ca2-552">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="95ca2-552">Hourly</span></span>     | <span data-ttu-id="95ca2-553">MX Co godzinę</span><span class="sxs-lookup"><span data-stu-id="95ca2-553">MX Hourly</span></span>   |
| <span data-ttu-id="95ca2-554">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="95ca2-554">Salaried</span></span>   | <span data-ttu-id="95ca2-555">MX Stała pensja</span><span class="sxs-lookup"><span data-stu-id="95ca2-555">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="95ca2-556">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="95ca2-556">Position types</span></span> 

<span data-ttu-id="95ca2-557">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="95ca2-557">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="95ca2-558">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="95ca2-558">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="95ca2-559">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-559">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-560">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="95ca2-560">Position type</span></span>   | <span data-ttu-id="95ca2-561">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-561">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="95ca2-562">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="95ca2-562">Full-time</span></span>       | <span data-ttu-id="95ca2-563">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="95ca2-563">Full time employee</span></span> |
| <span data-ttu-id="95ca2-564">Część etatu</span><span class="sxs-lookup"><span data-stu-id="95ca2-564">Part-time</span></span>       | <span data-ttu-id="95ca2-565">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="95ca2-565">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="95ca2-566">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="95ca2-566">Reason codes</span></span>

<span data-ttu-id="95ca2-567">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-567">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="95ca2-568">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="95ca2-568">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="95ca2-569">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-569">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-570">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="95ca2-570">Reason code</span></span>            | <span data-ttu-id="95ca2-571">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-571">Description</span></span>                    | <span data-ttu-id="95ca2-572">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="95ca2-572">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="95ca2-573">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="95ca2-573">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="95ca2-574">Odejście z pracy przed pierwszą wypłatą</span><span class="sxs-lookup"><span data-stu-id="95ca2-574">Departure before first payroll</span></span> | <span data-ttu-id="95ca2-575">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-575">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-576">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="95ca2-576">RESIGNATION</span></span>            | <span data-ttu-id="95ca2-577">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="95ca2-577">Resignation</span></span>                    | <span data-ttu-id="95ca2-578">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-578">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-579">PENSION</span><span class="sxs-lookup"><span data-stu-id="95ca2-579">PENSION</span></span>                | <span data-ttu-id="95ca2-580">Emerytura</span><span class="sxs-lookup"><span data-stu-id="95ca2-580">Pension</span></span>                        | <span data-ttu-id="95ca2-581">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-581">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-582">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="95ca2-582">TERMINATION</span></span>            | <span data-ttu-id="95ca2-583">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="95ca2-583">Termination</span></span>                    | <span data-ttu-id="95ca2-584">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-584">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-585">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="95ca2-585">RETIREMENT</span></span>             | <span data-ttu-id="95ca2-586">Emerytura</span><span class="sxs-lookup"><span data-stu-id="95ca2-586">Retirement</span></span>                     | <span data-ttu-id="95ca2-587">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-587">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-588">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="95ca2-588">ABSENTEE</span></span>               | <span data-ttu-id="95ca2-589">Absencja</span><span class="sxs-lookup"><span data-stu-id="95ca2-589">Absentee</span></span>                       | <span data-ttu-id="95ca2-590">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-590">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-591">INNY</span><span class="sxs-lookup"><span data-stu-id="95ca2-591">OTHER</span></span>                  | <span data-ttu-id="95ca2-592">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="95ca2-592">Other Reasons</span></span>                  | <span data-ttu-id="95ca2-593">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-593">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-594">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="95ca2-594">CLOSURE</span></span>                | <span data-ttu-id="95ca2-595">Zaprzestanie działalności przez firmę</span><span class="sxs-lookup"><span data-stu-id="95ca2-595">Business Closure</span></span>               | <span data-ttu-id="95ca2-596">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-596">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-597">DEATH</span><span class="sxs-lookup"><span data-stu-id="95ca2-597">DEATH</span></span>                  | <span data-ttu-id="95ca2-598">Śmierć</span><span class="sxs-lookup"><span data-stu-id="95ca2-598">Death</span></span>                          | <span data-ttu-id="95ca2-599">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-599">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-600">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="95ca2-600">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="95ca2-601">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="95ca2-601">Leave of Absence</span></span>               | <span data-ttu-id="95ca2-602">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-602">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-603">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="95ca2-603">CONTRACTEND</span></span>            | <span data-ttu-id="95ca2-604">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-604">End of Contract</span></span>                | <span data-ttu-id="95ca2-605">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="95ca2-605">Terminate worker</span></span>     |
| <span data-ttu-id="95ca2-606">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="95ca2-606">SALARYCHANGE</span></span>           | <span data-ttu-id="95ca2-607">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="95ca2-607">Change of Salary</span></span>               | <span data-ttu-id="95ca2-608">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-608">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="95ca2-609">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-609">Terms of employment</span></span>

<span data-ttu-id="95ca2-610">Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-610">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="95ca2-611">Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="95ca2-611">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="95ca2-612">Następujące warunki zatrudnienia i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="95ca2-612">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="95ca2-613">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-613">Terms of employment</span></span>   | <span data-ttu-id="95ca2-614">opis</span><span class="sxs-lookup"><span data-stu-id="95ca2-614">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="95ca2-615">Normalna</span><span class="sxs-lookup"><span data-stu-id="95ca2-615">Regular</span></span>               | <span data-ttu-id="95ca2-616">Normalna</span><span class="sxs-lookup"><span data-stu-id="95ca2-616">Regular</span></span>     |
| <span data-ttu-id="95ca2-617">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="95ca2-617">Direct</span></span>                | <span data-ttu-id="95ca2-618">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="95ca2-618">Direct</span></span>      |
| <span data-ttu-id="95ca2-619">Staż</span><span class="sxs-lookup"><span data-stu-id="95ca2-619">Internship</span></span>            | <span data-ttu-id="95ca2-620">Staż</span><span class="sxs-lookup"><span data-stu-id="95ca2-620">Internship</span></span>  |
| <span data-ttu-id="95ca2-621">Stałe</span><span class="sxs-lookup"><span data-stu-id="95ca2-621">Permanent</span></span>             | <span data-ttu-id="95ca2-622">Stałe</span><span class="sxs-lookup"><span data-stu-id="95ca2-622">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="95ca2-623">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="95ca2-623">Marital status</span></span>

<span data-ttu-id="95ca2-624">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-624">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95ca2-625">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-625">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="95ca2-626">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-626">Human Resources</span></span>                 | <span data-ttu-id="95ca2-627">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-627">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="95ca2-628">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="95ca2-628">Married</span></span>                | <span data-ttu-id="95ca2-629">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="95ca2-629">Married</span></span>                   |
| <span data-ttu-id="95ca2-630">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="95ca2-630">Single</span></span>                 | <span data-ttu-id="95ca2-631">Niebędący/niebędąca w związku</span><span class="sxs-lookup"><span data-stu-id="95ca2-631">Single</span></span>                    |
| <span data-ttu-id="95ca2-632">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="95ca2-632">Widowed</span></span>                | <span data-ttu-id="95ca2-633">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="95ca2-633">Widowed</span></span>                   |
| <span data-ttu-id="95ca2-634">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="95ca2-634">Divorced</span></span>               | <span data-ttu-id="95ca2-635">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="95ca2-635">Divorced</span></span>                  |
| <span data-ttu-id="95ca2-636">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="95ca2-636">Registered Partnership</span></span> | <span data-ttu-id="95ca2-637">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-637">Domestic Partnership</span></span>      |
| <span data-ttu-id="95ca2-638">None</span><span class="sxs-lookup"><span data-stu-id="95ca2-638">None</span></span>                   | <span data-ttu-id="95ca2-639">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-639">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95ca2-640">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="95ca2-640">Cohabiting</span></span>             | <span data-ttu-id="95ca2-641">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-641">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="95ca2-642">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="95ca2-642">Gender</span></span>

<span data-ttu-id="95ca2-643">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-643">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95ca2-644">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-644">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="95ca2-645">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-645">Human Resources</span></span>       | <span data-ttu-id="95ca2-646">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-646">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="95ca2-647">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="95ca2-647">Male</span></span>         | <span data-ttu-id="95ca2-648">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="95ca2-648">Male</span></span>                      |
| <span data-ttu-id="95ca2-649">Kobieta</span><span class="sxs-lookup"><span data-stu-id="95ca2-649">Female</span></span>       | <span data-ttu-id="95ca2-650">Kobieta</span><span class="sxs-lookup"><span data-stu-id="95ca2-650">Female</span></span>                    |
| <span data-ttu-id="95ca2-651">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="95ca2-651">Non-specific</span></span> | <span data-ttu-id="95ca2-652">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-652">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="95ca2-653">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="95ca2-653">Payment method</span></span>

<span data-ttu-id="95ca2-654">Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę.</span><span class="sxs-lookup"><span data-stu-id="95ca2-654">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="95ca2-655">Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-655">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="95ca2-656">W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-656">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="95ca2-657">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-657">Human Resources</span></span>             | <span data-ttu-id="95ca2-658">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-658">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="95ca2-659">Kasa</span><span class="sxs-lookup"><span data-stu-id="95ca2-659">Cash</span></span>               | <span data-ttu-id="95ca2-660">Kasa</span><span class="sxs-lookup"><span data-stu-id="95ca2-660">Cash</span></span>                      |
| <span data-ttu-id="95ca2-661">Płatność elektroniczna</span><span class="sxs-lookup"><span data-stu-id="95ca2-661">Electronic Payment</span></span> | <span data-ttu-id="95ca2-662">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="95ca2-662">Transfer</span></span>                  |
| <span data-ttu-id="95ca2-663">Sprawdzanie</span><span class="sxs-lookup"><span data-stu-id="95ca2-663">Check</span></span>              | <span data-ttu-id="95ca2-664">Czek</span><span class="sxs-lookup"><span data-stu-id="95ca2-664">Cheque</span></span>                    |
| <span data-ttu-id="95ca2-665">Przekaz bankowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-665">Bank Draft</span></span>         | <span data-ttu-id="95ca2-666">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-666">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95ca2-667">Inna</span><span class="sxs-lookup"><span data-stu-id="95ca2-667">Other</span></span>              | <span data-ttu-id="95ca2-668">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-668">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="95ca2-669">Typ konta bankowego</span><span class="sxs-lookup"><span data-stu-id="95ca2-669">Bank account type</span></span>

<span data-ttu-id="95ca2-670">Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="95ca2-670">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="95ca2-671">Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów.</span><span class="sxs-lookup"><span data-stu-id="95ca2-671">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="95ca2-672">Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="95ca2-672">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="95ca2-673">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-673">Human Resources</span></span>            | <span data-ttu-id="95ca2-674">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-674">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="95ca2-675">Konto czekowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-675">Checking Account</span></span>  | <span data-ttu-id="95ca2-676">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="95ca2-676">CheckingAccount</span></span>           |
| <span data-ttu-id="95ca2-677">Konto listy płac</span><span class="sxs-lookup"><span data-stu-id="95ca2-677">Payroll Account</span></span>   | <span data-ttu-id="95ca2-678">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="95ca2-678">PayrollAccount</span></span>            |
| <span data-ttu-id="95ca2-679">Konto oszczędnościowe</span><span class="sxs-lookup"><span data-stu-id="95ca2-679">Savings Account</span></span>   | <span data-ttu-id="95ca2-680">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95ca2-681">Konto BankGirot</span><span class="sxs-lookup"><span data-stu-id="95ca2-681">BankGirot account</span></span> | <span data-ttu-id="95ca2-682">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-682">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="95ca2-683">Konto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="95ca2-683">PlusGirot account</span></span> | <span data-ttu-id="95ca2-684">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="95ca2-684">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="95ca2-685">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="95ca2-685">Earning codes</span></span>

<span data-ttu-id="95ca2-686">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="95ca2-686">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="95ca2-687">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="95ca2-687">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="95ca2-688">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-688">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="95ca2-689">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="95ca2-689">Supported frequencies</span></span>

- <span data-ttu-id="95ca2-690">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="95ca2-690">All</span></span>
- <span data-ttu-id="95ca2-691">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="95ca2-691">EVERYPAY</span></span>
- <span data-ttu-id="95ca2-692">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="95ca2-692">EACHPAYPERIOD</span></span>
- <span data-ttu-id="95ca2-693">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="95ca2-693">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="95ca2-694">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="95ca2-694">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="95ca2-695">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-695">1OFMTH</span></span>
- <span data-ttu-id="95ca2-696">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-696">LASTOFMTH</span></span>
- <span data-ttu-id="95ca2-697">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-697">2OFMTH</span></span>
- <span data-ttu-id="95ca2-698">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-698">3OFMTH</span></span>
- <span data-ttu-id="95ca2-699">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-699">4OFMTH</span></span>
- <span data-ttu-id="95ca2-700">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-700">5OFMTH</span></span>
- <span data-ttu-id="95ca2-701">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-701">1N2OFMTH</span></span>
- <span data-ttu-id="95ca2-702">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-702">3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-703">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-703">1N3OFMTH</span></span>
- <span data-ttu-id="95ca2-704">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-704">1N4OFMTH</span></span>
- <span data-ttu-id="95ca2-705">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-705">2N3OFMTH</span></span>
- <span data-ttu-id="95ca2-706">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-706">2N4OFMTH</span></span>
- <span data-ttu-id="95ca2-707">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-707">1N2N3OFMTH</span></span>
- <span data-ttu-id="95ca2-708">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-708">1N2N4OFMTH</span></span>
- <span data-ttu-id="95ca2-709">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-709">1N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-710">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-710">2N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-711">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="95ca2-711">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="95ca2-712">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="95ca2-712">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="95ca2-713">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-713">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="95ca2-714">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-714">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="95ca2-715">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="95ca2-715">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="95ca2-716">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-716">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="95ca2-717">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-717">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="95ca2-718">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="95ca2-718">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="95ca2-719">Adresy</span><span class="sxs-lookup"><span data-stu-id="95ca2-719">Addresses</span></span>

<span data-ttu-id="95ca2-720">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="95ca2-720">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="95ca2-721">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="95ca2-721">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="95ca2-722">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="95ca2-722">Human Resources</span></span>              | <span data-ttu-id="95ca2-723">Dayforce</span><span class="sxs-lookup"><span data-stu-id="95ca2-723">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="95ca2-724">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="95ca2-724">Country/Region</span></span>      | <span data-ttu-id="95ca2-725">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="95ca2-725">Country Code</span></span>          |
| <span data-ttu-id="95ca2-726">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-726">Zip/Postal Code</span></span>     | <span data-ttu-id="95ca2-727">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-727">Postal Code</span></span>           |
| <span data-ttu-id="95ca2-728">Stanowy</span><span class="sxs-lookup"><span data-stu-id="95ca2-728">State</span></span>               | <span data-ttu-id="95ca2-729">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="95ca2-729">State Code</span></span>            |
| <span data-ttu-id="95ca2-730">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="95ca2-730">City</span></span>                | <span data-ttu-id="95ca2-731">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="95ca2-731">City</span></span>                  |
| <span data-ttu-id="95ca2-732">Powiat</span><span class="sxs-lookup"><span data-stu-id="95ca2-732">County</span></span>              | <span data-ttu-id="95ca2-733">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="95ca2-733">County (Municipality)</span></span> |
| <span data-ttu-id="95ca2-734">Ulica</span><span class="sxs-lookup"><span data-stu-id="95ca2-734">Street</span></span>              | <span data-ttu-id="95ca2-735">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="95ca2-735">Address Line 1</span></span>        |
| <span data-ttu-id="95ca2-736">Numer budynku</span><span class="sxs-lookup"><span data-stu-id="95ca2-736">Street Number</span></span>       | <span data-ttu-id="95ca2-737">Wiersz adresu 2</span><span class="sxs-lookup"><span data-stu-id="95ca2-737">Address Line 2</span></span>        |
| <span data-ttu-id="95ca2-738">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="95ca2-738">Building Complement</span></span> | <span data-ttu-id="95ca2-739">Wiersz adresu 5</span><span class="sxs-lookup"><span data-stu-id="95ca2-739">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="95ca2-740">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="95ca2-740">Passport number</span></span>

<span data-ttu-id="95ca2-741">Pracownicy mogą podać informacje z paszportów.</span><span class="sxs-lookup"><span data-stu-id="95ca2-741">Employees can declare passport information.</span></span> <span data-ttu-id="95ca2-742">Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="95ca2-742">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="95ca2-743">Typ identyfikacji = „Paszport”</span><span class="sxs-lookup"><span data-stu-id="95ca2-743">Identification Type = "Passport"</span></span>
- <span data-ttu-id="95ca2-744">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="95ca2-744">Issued Date</span></span>
- <span data-ttu-id="95ca2-745">Data ważności</span><span class="sxs-lookup"><span data-stu-id="95ca2-745">Expiration Date</span></span>

<span data-ttu-id="95ca2-746">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**.</span><span class="sxs-lookup"><span data-stu-id="95ca2-746">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="95ca2-747">Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce.</span><span class="sxs-lookup"><span data-stu-id="95ca2-747">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="95ca2-748">Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.</span><span class="sxs-lookup"><span data-stu-id="95ca2-748">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]