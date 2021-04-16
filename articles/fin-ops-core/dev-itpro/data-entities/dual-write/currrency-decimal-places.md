---
title: Migracja typu danych Waluta dla podwójnego zapisu
description: W tym temacie opisano sposób zmiany liczby miejsc dziesiętnych, które podwójny zapis obsługuje dla waluty.
author: RamaKrishnamoorthy
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: c4f663ae36f7d4ea3db9888e618f2fe3bf8c3256
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748954"
---
# <a name="currency-data-type-migration-for-dual-write"></a><span data-ttu-id="9c45c-103">Migracja typu danych Waluta dla podwójnego zapisu</span><span class="sxs-lookup"><span data-stu-id="9c45c-103">Currency data-type migration for dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9c45c-104">Można zwiększyć liczbę miejsc dziesiętnych, które są obsługiwane dla wartości walut, do maksymalnie 10.</span><span class="sxs-lookup"><span data-stu-id="9c45c-104">You can increase the number of decimal places that are supported for currency values to a maximum of 10.</span></span> <span data-ttu-id="9c45c-105">Domyślny limit to cztery miejsca po przecinku.</span><span class="sxs-lookup"><span data-stu-id="9c45c-105">The default limit is four decimal places.</span></span> <span data-ttu-id="9c45c-106">Zwiększenie liczby miejsc po przecinku pozwala zapobiec utracie danych podczas używania funkcji podwójnego zapisywania w celu zsynchronizowania danych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-106">By increasing the number of decimal places, you help prevent data loss when you use dual-write to sync data.</span></span> <span data-ttu-id="9c45c-107">Zwiększenie liczby miejsc dziesiętnych jest zmianą do wyboru.</span><span class="sxs-lookup"><span data-stu-id="9c45c-107">The increase in the number of decimal places is an opt-in change.</span></span> <span data-ttu-id="9c45c-108">Aby go zaimplementować, musisz zażądać pomocy od firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9c45c-108">To implement it, you must request assistance from Microsoft.</span></span>

<span data-ttu-id="9c45c-109">Proces zmiany liczby miejsc dziesiętnych składa się z dwóch kroków:</span><span class="sxs-lookup"><span data-stu-id="9c45c-109">The process of changing the number of decimal places has two steps:</span></span>

1. <span data-ttu-id="9c45c-110">Zażądaj migracji z rozwiązania Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9c45c-110">Request migration from Microsoft.</span></span>
2. <span data-ttu-id="9c45c-111">Zmienianie liczby miejsc po przecinku w Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c45c-111">Change the number of decimal places in Dataverse.</span></span>

<span data-ttu-id="9c45c-112">Aplikacja Finance and Operations i Dataverse muszą obsługiwać tę samą liczbę miejsc dziesiętnych w wartościach walutowych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-112">The Finance and Operations app and Dataverse must support the same number of decimal places in currency values.</span></span> <span data-ttu-id="9c45c-113">W przeciwnym razie utrata danych może wystąpić, gdy informacje te zostaną zsynchronizowane między aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="9c45c-113">Otherwise, data loss can occur when this information is synced between apps.</span></span> <span data-ttu-id="9c45c-114">Proces migracji zmienia konfigurację sposobu przechowywania wartości walut i kursów wymiany, ale nie powoduje zmiany żadnych danych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-114">The migration process reconfigures the way that currency and exchange rate values are stored, but it doesn't change any data.</span></span> <span data-ttu-id="9c45c-115">Po zakończeniu migracji liczba miejsc dziesiętnych dla kodów walut i cen może zostać zwiększona, a dane wprowadzane przez użytkowników i widok mogą mieć większą dokładność dziesiętną.</span><span class="sxs-lookup"><span data-stu-id="9c45c-115">After the migration is completed, the number of decimal places for currency codes and pricing can be increased, and the data that users enter and view can have more decimal precision.</span></span>

<span data-ttu-id="9c45c-116">Migracja jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="9c45c-116">Migration is optional.</span></span> <span data-ttu-id="9c45c-117">Jeśli można korzystać z pomocy technicznej dla większej liczby miejsc dziesiętnych, zaleca się, aby wziąć pod uwagę migrację.</span><span class="sxs-lookup"><span data-stu-id="9c45c-117">If you might benefit from support for more decimal places, we recommend that you consider migration.</span></span> <span data-ttu-id="9c45c-118">Organizacje niewymagające wartości, które mają więcej niż cztery miejsca dziesiętne, nie muszą migrować.</span><span class="sxs-lookup"><span data-stu-id="9c45c-118">Organizations that don't require values that have more than four decimal places don't have to migrate.</span></span>

## <a name="requesting-migration-from-microsoft"></a><span data-ttu-id="9c45c-119">Żądanie migracji od Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c45c-119">Requesting migration from Microsoft</span></span>

<span data-ttu-id="9c45c-120">Przechowywanie w istniejących kolumnach waluty w Dataverse nie obsługuje więcej niż czterech miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-120">Storage for existing currency columns in Dataverse can't support more than four decimal places.</span></span> <span data-ttu-id="9c45c-121">Dlatego podczas procesu migracji wartości walut są kopiowane do nowych kolumn wewnętrznych w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-121">Therefore, during the migration process, currency values are copied to new internal columns in the database.</span></span> <span data-ttu-id="9c45c-122">Ten proces jest wykonywany w sposób ciągły, dopóki nie zostaną zmigrowane wszystkie dane.</span><span class="sxs-lookup"><span data-stu-id="9c45c-122">This process occurs continuously until all data has been migrated.</span></span> <span data-ttu-id="9c45c-123">Wewnętrznie na zakończenie migracji nowe typy magazynów zastępują stare typy magazynów, ale wartości danych nie są zmieniane.</span><span class="sxs-lookup"><span data-stu-id="9c45c-123">Internally, at the end of migration, the new storage types replace the old storage types, but the data values are unchanged.</span></span> <span data-ttu-id="9c45c-124">Następnie kolumny waluty mogą obsługiwać maksymalnie 10 miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-124">The currency columns can then support up to 10 decimal places.</span></span> <span data-ttu-id="9c45c-125">W trakcie procesu migracji Dataverse może nadal korzystać z systemu bez zakłóceń.</span><span class="sxs-lookup"><span data-stu-id="9c45c-125">During the migration process, Dataverse can continue to be used without interruption.</span></span>

<span data-ttu-id="9c45c-126">W tym samym czasie kursy wymiany są modyfikowane w taki sposób, aby obsługiwały maksymalnie 12 miejsc dziesiętnych zamiast bieżącego limitu wynoszący 10.</span><span class="sxs-lookup"><span data-stu-id="9c45c-126">At the same time, exchange rates are modified so that they support up to 12 decimal places instead of the current limit of 10.</span></span> <span data-ttu-id="9c45c-127">Ta zmiana jest wymagana w celu zapewnienia, że liczba miejsc dziesiętnych jest taka sama w obu wersjach aplikacji Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9c45c-127">This change is required so that the number of decimal places is the same in both the Finance and Operations app and Dataverse.</span></span>

<span data-ttu-id="9c45c-128">Migracja nie powoduje zmiany żadnych danych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-128">Migration doesn't change any data.</span></span> <span data-ttu-id="9c45c-129">Po przekonwertowaniu kolumn waluta i kurs wymiany administratorzy mogą skonfigurować system do 10 miejsc dziesiętnych dla kolumn walut, określając liczbę miejsc dziesiętnych dla każdej waluty transakcji i ceny.</span><span class="sxs-lookup"><span data-stu-id="9c45c-129">After the currency and exchange rate columns are converted, admins can configure the system to use up to 10 decimal places for currency columns by specifying the number of decimal places for each transaction currency and for pricing.</span></span>

### <a name="request-a-migration"></a><span data-ttu-id="9c45c-130">Żądaj migracji</span><span class="sxs-lookup"><span data-stu-id="9c45c-130">Request a migration</span></span>

<span data-ttu-id="9c45c-131">Aby udostępnić tę funkcję, wyślij wiadomość e-mail na **CDSExpandDecimal@microsoft.com** i uwzględnij następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="9c45c-131">To make this feature available, email **CDSExpandDecimal@microsoft.com**, and include the following information:</span></span>

+ <span data-ttu-id="9c45c-132">**Temat:** Żądanie włączenia obsługi rozszerzonego miejsca dziesiętnego dla \<organizationID\></span><span class="sxs-lookup"><span data-stu-id="9c45c-132">**Subject:** Request to enable expanded decimal support for \<organizationID\></span></span>
+ <span data-ttu-id="9c45c-133">**Treść:** Chcę włączyć rozszerzoną obsługę miejsc dziesiętnych dla mojej organizacji \<organizationID\>.</span><span class="sxs-lookup"><span data-stu-id="9c45c-133">**Body:** I would like to enable expanded decimal support for my org \<organizationID\>.</span></span>

<span data-ttu-id="9c45c-134">Przedstawiciel firmy Microsoft skontaktuje się z Tobą w ciągu dwóch do trzech dni roboczych dla kolejnych kroków.</span><span class="sxs-lookup"><span data-stu-id="9c45c-134">A Microsoft representative will contact you within two to three business days for the next steps.</span></span>

<span data-ttu-id="9c45c-135">Podczas składania wniosku o migrację należy zwrócić uwagę na następujące szczegóły i ich odpowiedni plan:</span><span class="sxs-lookup"><span data-stu-id="9c45c-135">When you request a migration, you should be aware of the following details and plan for them accordingly:</span></span>

+ <span data-ttu-id="9c45c-136">Czas wymagany do migrowania danych zależy od ilości danych w systemie.</span><span class="sxs-lookup"><span data-stu-id="9c45c-136">The time that is required to migrate the data depends the amount of data in the system.</span></span> <span data-ttu-id="9c45c-137">Migracja dużych baz danych może trwać kilka dni.</span><span class="sxs-lookup"><span data-stu-id="9c45c-137">Migration of large databases can take several days.</span></span>
+ <span data-ttu-id="9c45c-138">Rozmiar bazy danych jest tymczasowo zwiększany podczas działania migracji, ponieważ potrzebne jest dodatkowe miejsce dla indeksów.</span><span class="sxs-lookup"><span data-stu-id="9c45c-138">The size of the database temporarily increases while the migration is running, because additional space is needed for indexes.</span></span> <span data-ttu-id="9c45c-139">Większość dodatkowych miejsc jest zwalniana po zakończeniu migracji.</span><span class="sxs-lookup"><span data-stu-id="9c45c-139">Most of the additional space is freed when the migration is completed.</span></span>
+ <span data-ttu-id="9c45c-140">W trakcie procesu migracji, jeśli wystąpią błędy, co uniemożliwia zakończenie migracji, system zgłosi alerty do pomocy technicznej firmy Microsoft, dzięki czemu pracownik pomocy technicznej będzie mógł interweniować.</span><span class="sxs-lookup"><span data-stu-id="9c45c-140">During the migration process, if errors occur that prevent the migration from being completed, the system raise alerts to Microsoft Support, so that Support staff can intervene.</span></span> <span data-ttu-id="9c45c-141">Jednak nawet jeśli podczas migracji wystąpią błędy, Dataverse pozostanie w pełni dostępny do normalnego użycia.</span><span class="sxs-lookup"><span data-stu-id="9c45c-141">However, even if errors occur during the migration, Dataverse remains fully available for regular use.</span></span>
+ <span data-ttu-id="9c45c-142">Proces migracji nie jest odwracalny.</span><span class="sxs-lookup"><span data-stu-id="9c45c-142">The migration process isn't reversible.</span></span>

## <a name="changing-the-number-of-decimal-places"></a><span data-ttu-id="9c45c-143">Zmienianie liczby miejsc po przecinku</span><span class="sxs-lookup"><span data-stu-id="9c45c-143">Changing the number of decimal places</span></span>

<span data-ttu-id="9c45c-144">Po zakończeniu migracji Dataverse możne przechowywać numery zawierające więcej miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-144">After the migration is completed, Dataverse can store numbers that have more decimal places.</span></span> <span data-ttu-id="9c45c-145">Administratorzy mogą określić, ile miejsc dziesiętnych ma być używanych dla konkretnych kodów walut i cen.</span><span class="sxs-lookup"><span data-stu-id="9c45c-145">Admins can choose how many decimal places are used for specific currency codes and for pricing.</span></span> <span data-ttu-id="9c45c-146">Użytkownicy Microsoft Power Apps, Power BI, a Power Automate następnie mogą przeglądać i stosować liczby zawierające więcej miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="9c45c-146">Users of Microsoft Power Apps, Power BI, and Power Automate can then view and use numbers that have more decimal places.</span></span>

<span data-ttu-id="9c45c-147">Aby wprowadzić tę zmianę, należy zaktualizować następujące ustawienia w Power Apps:</span><span class="sxs-lookup"><span data-stu-id="9c45c-147">To make this change, you must update the following settings in Power Apps:</span></span>

+ <span data-ttu-id="9c45c-148">**Ustawienia systemowe: dokładność waluty dla ceny** — kolumna **Ustaw dokładność waluty, która jest używana do ustalania cen w całym systemie** określa sposób zachowania się waluty w przypadku wybrania **Precyzji wyceny**.</span><span class="sxs-lookup"><span data-stu-id="9c45c-148">**System Settings: Currency precision for pricing** – The **Set the currency precision that is used for pricing throughout the system** column defines how the currency will behave for the organization when **Pricing Precision** is selected.</span></span>
+ <span data-ttu-id="9c45c-149">**Zarządzanie firmą: waluty** — kolumna **Dokładność waluty** umożliwia określenie niestandardowej liczby miejsc dziesiętnych dla określonej waluty.</span><span class="sxs-lookup"><span data-stu-id="9c45c-149">**Business Management: Currencies** – The **Currency Precision** column lets you specify a custom number of decimal places for a specific currency.</span></span> <span data-ttu-id="9c45c-150">Istnieje powrót do ustawienia dotyczącego całej organizacji.</span><span class="sxs-lookup"><span data-stu-id="9c45c-150">There is a fallback to the organization-wide setting.</span></span>

<span data-ttu-id="9c45c-151">Istnieją pewne ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="9c45c-151">There are some limitations:</span></span>

+ <span data-ttu-id="9c45c-152">Nie można skonfigurować kolumny waluty w tabeli.</span><span class="sxs-lookup"><span data-stu-id="9c45c-152">You can't configure the currency column on a table.</span></span>
+ <span data-ttu-id="9c45c-153">Można określić więcej niż cztery miejsca dziesiętne tylko na poziomach **Ceny** i **Waluta transakcji**.</span><span class="sxs-lookup"><span data-stu-id="9c45c-153">You can specify more than four decimal places only at the **Pricing** and **Transaction Currency** levels.</span></span>

### <a name="system-settings-currency-precision-for-pricing"></a><span data-ttu-id="9c45c-154">Ustawienia systemowe: dokładność waluty dla ceny</span><span class="sxs-lookup"><span data-stu-id="9c45c-154">System Settings: Currency precision for pricing</span></span>

<span data-ttu-id="9c45c-155">Po zakończeniu migracji Administratorzy mogą skonfigurować dokładność waluty.</span><span class="sxs-lookup"><span data-stu-id="9c45c-155">After migration is completed, admins can set the currency precision.</span></span> <span data-ttu-id="9c45c-156">Przejdź do **Ustawienia \> Administracja** i wybierz **Ustawienia systemowe**.</span><span class="sxs-lookup"><span data-stu-id="9c45c-156">Go to **Settings \> Administration**, and select **System Settings**.</span></span> <span data-ttu-id="9c45c-157">Następnie na karcie **Ogólne** zmień wartość kolumny **Ustaw dokładność waluty, która jest używana do ustalania cen w całym systemie**, co pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="9c45c-157">Then, on the **General** tab, change the value of the **Set the currency precision that is used for pricing throughout the system** column, as shown in the following illustration.</span></span>

![Ustawienia systemowe dla waluty](media/currency-system-settings.png)

### <a name="business-management-currencies"></a><span data-ttu-id="9c45c-159">Zarządzanie firmą: waluty</span><span class="sxs-lookup"><span data-stu-id="9c45c-159">Business Management: Currencies</span></span>

<span data-ttu-id="9c45c-160">Jeśli precyzja waluty dla konkretnej waluty różni się od precyzji waluty używanej do ustalania cen, można ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="9c45c-160">If you require that the currency precision for a specific currency differ from the currency precision that is used for pricing, you can change it.</span></span> <span data-ttu-id="9c45c-161">Przejdź do **Ustawienia \> Zarządzanie firmą**, wybierz opcję **Waluty** i wybierz walutę, która ma zostać zmieniona.</span><span class="sxs-lookup"><span data-stu-id="9c45c-161">Go to **Settings \> Business Management**, select **Currencies**, and select the currency to change.</span></span> <span data-ttu-id="9c45c-162">Następnie w kolumnie **Dokładność waluty** należy określić żądaną liczbę miejsc dziesiętnych, jak to pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="9c45c-162">Then set the **Currency Precision** column to the number of decimal places that you want, as shown in the following illustration.</span></span>

![Ustawienia waluty dla określonego ustawienia regionalnego](media/specific-currency.png)

### <a name="tables-currency-column"></a><span data-ttu-id="9c45c-164">tabele: kolumna Waluta</span><span class="sxs-lookup"><span data-stu-id="9c45c-164">tables: Currency column</span></span>

<span data-ttu-id="9c45c-165">Liczba miejsc dziesiętnych, które można skonfigurować dla określonych kolumn waluty, jest ograniczona do czterech.</span><span class="sxs-lookup"><span data-stu-id="9c45c-165">The number of decimal places that can be configured for specific currency columns is limited to four.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]