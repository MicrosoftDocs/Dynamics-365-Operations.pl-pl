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
# <a name="currency-data-type-migration-for-dual-write"></a>Migracja typu danych Waluta dla podwójnego zapisu

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Można zwiększyć liczbę miejsc dziesiętnych, które są obsługiwane dla wartości walut, do maksymalnie 10. Domyślny limit to cztery miejsca po przecinku. Zwiększenie liczby miejsc po przecinku pozwala zapobiec utracie danych podczas używania funkcji podwójnego zapisywania w celu zsynchronizowania danych. Zwiększenie liczby miejsc dziesiętnych jest zmianą do wyboru. Aby go zaimplementować, musisz zażądać pomocy od firmy Microsoft.

Proces zmiany liczby miejsc dziesiętnych składa się z dwóch kroków:

1. Zażądaj migracji z rozwiązania Microsoft.
2. Zmienianie liczby miejsc po przecinku w Dataverse.

Aplikacja Finance and Operations i Dataverse muszą obsługiwać tę samą liczbę miejsc dziesiętnych w wartościach walutowych. W przeciwnym razie utrata danych może wystąpić, gdy informacje te zostaną zsynchronizowane między aplikacjami. Proces migracji zmienia konfigurację sposobu przechowywania wartości walut i kursów wymiany, ale nie powoduje zmiany żadnych danych. Po zakończeniu migracji liczba miejsc dziesiętnych dla kodów walut i cen może zostać zwiększona, a dane wprowadzane przez użytkowników i widok mogą mieć większą dokładność dziesiętną.

Migracja jest opcjonalna. Jeśli można korzystać z pomocy technicznej dla większej liczby miejsc dziesiętnych, zaleca się, aby wziąć pod uwagę migrację. Organizacje niewymagające wartości, które mają więcej niż cztery miejsca dziesiętne, nie muszą migrować.

## <a name="requesting-migration-from-microsoft"></a>Żądanie migracji od Microsoft

Przechowywanie w istniejących kolumnach waluty w Dataverse nie obsługuje więcej niż czterech miejsc dziesiętnych. Dlatego podczas procesu migracji wartości walut są kopiowane do nowych kolumn wewnętrznych w bazie danych. Ten proces jest wykonywany w sposób ciągły, dopóki nie zostaną zmigrowane wszystkie dane. Wewnętrznie na zakończenie migracji nowe typy magazynów zastępują stare typy magazynów, ale wartości danych nie są zmieniane. Następnie kolumny waluty mogą obsługiwać maksymalnie 10 miejsc dziesiętnych. W trakcie procesu migracji Dataverse może nadal korzystać z systemu bez zakłóceń.

W tym samym czasie kursy wymiany są modyfikowane w taki sposób, aby obsługiwały maksymalnie 12 miejsc dziesiętnych zamiast bieżącego limitu wynoszący 10. Ta zmiana jest wymagana w celu zapewnienia, że liczba miejsc dziesiętnych jest taka sama w obu wersjach aplikacji Finance and Operations i Dataverse.

Migracja nie powoduje zmiany żadnych danych. Po przekonwertowaniu kolumn waluta i kurs wymiany administratorzy mogą skonfigurować system do 10 miejsc dziesiętnych dla kolumn walut, określając liczbę miejsc dziesiętnych dla każdej waluty transakcji i ceny.

### <a name="request-a-migration"></a>Żądaj migracji

Aby udostępnić tę funkcję, wyślij wiadomość e-mail na **CDSExpandDecimal@microsoft.com** i uwzględnij następujące informacje:

+ **Temat:** Żądanie włączenia obsługi rozszerzonego miejsca dziesiętnego dla \<organizationID\>
+ **Treść:** Chcę włączyć rozszerzoną obsługę miejsc dziesiętnych dla mojej organizacji \<organizationID\>.

Przedstawiciel firmy Microsoft skontaktuje się z Tobą w ciągu dwóch do trzech dni roboczych dla kolejnych kroków.

Podczas składania wniosku o migrację należy zwrócić uwagę na następujące szczegóły i ich odpowiedni plan:

+ Czas wymagany do migrowania danych zależy od ilości danych w systemie. Migracja dużych baz danych może trwać kilka dni.
+ Rozmiar bazy danych jest tymczasowo zwiększany podczas działania migracji, ponieważ potrzebne jest dodatkowe miejsce dla indeksów. Większość dodatkowych miejsc jest zwalniana po zakończeniu migracji.
+ W trakcie procesu migracji, jeśli wystąpią błędy, co uniemożliwia zakończenie migracji, system zgłosi alerty do pomocy technicznej firmy Microsoft, dzięki czemu pracownik pomocy technicznej będzie mógł interweniować. Jednak nawet jeśli podczas migracji wystąpią błędy, Dataverse pozostanie w pełni dostępny do normalnego użycia.
+ Proces migracji nie jest odwracalny.

## <a name="changing-the-number-of-decimal-places"></a>Zmienianie liczby miejsc po przecinku

Po zakończeniu migracji Dataverse możne przechowywać numery zawierające więcej miejsc dziesiętnych. Administratorzy mogą określić, ile miejsc dziesiętnych ma być używanych dla konkretnych kodów walut i cen. Użytkownicy Microsoft Power Apps, Power BI, a Power Automate następnie mogą przeglądać i stosować liczby zawierające więcej miejsc dziesiętnych.

Aby wprowadzić tę zmianę, należy zaktualizować następujące ustawienia w Power Apps:

+ **Ustawienia systemowe: dokładność waluty dla ceny** — kolumna **Ustaw dokładność waluty, która jest używana do ustalania cen w całym systemie** określa sposób zachowania się waluty w przypadku wybrania **Precyzji wyceny**.
+ **Zarządzanie firmą: waluty** — kolumna **Dokładność waluty** umożliwia określenie niestandardowej liczby miejsc dziesiętnych dla określonej waluty. Istnieje powrót do ustawienia dotyczącego całej organizacji.

Istnieją pewne ograniczenia:

+ Nie można skonfigurować kolumny waluty w tabeli.
+ Można określić więcej niż cztery miejsca dziesiętne tylko na poziomach **Ceny** i **Waluta transakcji**.

### <a name="system-settings-currency-precision-for-pricing"></a>Ustawienia systemowe: dokładność waluty dla ceny

Po zakończeniu migracji Administratorzy mogą skonfigurować dokładność waluty. Przejdź do **Ustawienia \> Administracja** i wybierz **Ustawienia systemowe**. Następnie na karcie **Ogólne** zmień wartość kolumny **Ustaw dokładność waluty, która jest używana do ustalania cen w całym systemie**, co pokazano na poniższej ilustracji.

![Ustawienia systemowe dla waluty](media/currency-system-settings.png)

### <a name="business-management-currencies"></a>Zarządzanie firmą: waluty

Jeśli precyzja waluty dla konkretnej waluty różni się od precyzji waluty używanej do ustalania cen, można ją zmienić. Przejdź do **Ustawienia \> Zarządzanie firmą**, wybierz opcję **Waluty** i wybierz walutę, która ma zostać zmieniona. Następnie w kolumnie **Dokładność waluty** należy określić żądaną liczbę miejsc dziesiętnych, jak to pokazano na poniższej ilustracji.

![Ustawienia waluty dla określonego ustawienia regionalnego](media/specific-currency.png)

### <a name="tables-currency-column"></a>tabele: kolumna Waluta

Liczba miejsc dziesiętnych, które można skonfigurować dla określonych kolumn waluty, jest ograniczona do czterech.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]