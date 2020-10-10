---
title: Konfigurowanie i używanie wstrzymań zamówień w biurze obsługi
description: W tym temacie opisano sposób pracy ze wstrzymaniami zamówień za pomocą Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans, MCROrderEventSetup, MCROrderEventTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b11dd48ac629910a82b4d5bfdf9889809b0d829d
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830130"
---
# <a name="configure-and-work-with-call-center-order-holds"></a>Konfigurowanie i używanie wstrzymań zamówień w biurze obsługi

[!include [banner](includes/banner.md)]

W tym temacie opisano funkcje wstrzymania zamówienia dostępne w Dynamics 365 Commerce dla zamówień w biurze obsługi telefonicznej.

## <a name="configuring-call-center-order-holds"></a>Konfigurowanie wstrzymań zamówień w biurze obsługi

Korzystać z funkcji wstrzymania zamówienia produkcyjnego w biurze obsługi, należy najpierw zdefiniować kody wstrzymania. Aby utworzyć zestaw kodów wstrzymania zdefiniowanych przez użytkownika zgodnie z wymaganiami firmy, przejdź do **Moduł sprzedaży i marketingu** \> **ustawienia** \> **zamówienia sprzedaży** \> **kody wstrzymania zamówień**. Opcjonalnie można oznaczyć flagą jeden z kodów wstrzymania jako domyślny, ustawiając dla opcji **Domyślnie dla zamówienia sprzedaży** tego kodu wartość **tak**. Ten kod wstrzymania zostanie użyty w momencie wstrzymania zamówienia sprzedaży. Jeśli zamówienie sprzedaży ma zarezerwowane zapasy, a rezerwacje muszą zostać automatycznie usunięte, jeśli zamówienie zostanie wstrzymane z jakiegokolwiek powodu, w sekcji kodów przyczyn w ustawieniu **Usuń rezerwacje zapasów** zaznacz opcję **Tak**.

Aby określić typ notatki, która, zostanie przechwycona po wprowadzeniu przez użytkowników wstrzymujących zamówienie sprzedaży opcjonalnej notatki, przejdź do **Rozrachunki z odbiorcami** \> **Ustawienia** \> **Parametry rozrachunków z odbiorcami**, a następnie w skróconej karcie **Ustawienia sprzedaży** w zakładce **Ogólne** należy ustawić pole **Typ notatki**. Użyj pola **Status wstrzymanego zamówienia sprzedaży**, aby określić kolor, który będzie używany do wyróżnienia zamówień sprzedaży, które są wstrzymane w czasie podglądu na stronie **Obsługi klienta**.

Aby utworzyć opcjonalny zbiór kodów przyczyn wstrzymania, przejdź do **Sprzedaż detaliczna i inna** \> **Konfiguracja kanału** \> **Kody informacji**. Te kody informacyjne mogą zostać wykorzystane jako pomocniczy kod przyczyny w celu szczegółowego zdefiniowania głównego kodu wstrzymania. Wybierz opcję **Nowy**, aby utworzyć zestaw kodów przyczyn, a następnie wybierz opcję **Kody podrzędne**, aby zdefiniować listę dodatkowych przyczyn. Aby połączyć wszelkie kody informacje zdefiniowane dla kanału biura obsługi, przejdź do **Sprzedaż detaliczna i inna** \> **Kanały** \> **Biura obsługi** \> **Wszystkie biura obsługi**. Na skróconej karcie **Ogólne** włącz pole **Kod wstrzymania**.

## <a name="putting-orders-on-hold"></a>Wstrzymywanie zamówień

Zamówienia tworzone przez użytkowników biura obsług w programie Commerce działającym na zapleczu mogą być wstrzymywane ręcznie lub automatycznie w określonych sytuacjach.

Podczas wprowadzania zamówienia, ale przed jego przesłaniem i potwierdzeniem biuro, użytkownicy w biurze obsługi mogą chcieć ręcznie wstrzymać zamówienie, aby uniemożliwić jego zwolnienie do magazynu w celu dalszego przetwarzania. Na przykład odbiorca składający zamówienie może nie być gotowy do jego potwierdzenia albo brakuje krytycznych danych, które są wymagane w celu przetworzenia zamówienia.

Na stronie wprowadzania zamówień użytkownik centrum obsługi może wstrzymać zamówienie za pomocą opcji **Wstrzymania zamówień** znajdującej się na karcie **Zamówienie sprzedaży** w menu wprowadzania zamówień. Alternatywnie użytkownik może wybrać elementu menu **Wstrzymanie** dostępny na stronie **Podsumowanie zamówienia sprzedaży** wyświetlanej po kliknięciu opcji **Zakończ** w zamówieniu sprzedaży biura obsługi.

W obu przypadkach zostanie wyświetlona strona **Wstrzymania zamówień**. Użytkownik może następnie wybrać opcję **Nowy**, aby utworzyć wstrzymanie dla zamówienia. W polu **Kod wstrzymania** użytkownik powinien wybrać kod, który najlepiej opisuje przyczynę wstrzymania. W polu **Kod przyczyny** użytkownik może opcjonalnie wybrać dodatkowy kod, aby podać drugi poziom opisu wstrzymania.

Na skróconej karcie **Uwagi** w polu **Notatki dotyczące wstrzymania** użytkownik może wprowadzić dodatkowe, dowolne notatki przedstawiające dodatkowy kontekst lub informacje o wstrzymaniu. Te notatki mogą pomóc innym użytkownikom sprawdzającym później wstrzymane zamówienie lub pracującym nad nim.

Po wprowadzeniu i zapisaniu informacji o wstrzymaniu użytkownik może zamknąć stronę **Wstrzymania zamówień**. Użytkownik następnie zostaje skierowany ponownie do strony wprowadzania zamówienia sprzedaży. Jeśli nie są wymagane żadne dalsze działania na zamówieniu sprzedaży, użytkownik może zamknąć stronę wprowadzania zamówienia sprzedaży.

Jeśli flaga **Włącz kończenie zamówienia** jest włączona w kanale biura obsługi, płatność nie musi być stosowana do wstrzymanego zamówienia. Z drugiej strony w przypadku zamówienia sprzedaży, które nie jest wstrzymane, użytkownicy nie mogą opuścić strony wprowadzania zamówienia do momentu zastosowania płatności. Oczywiście przed zwolnieniem wstrzymania zamówienia musi zostać dokonana płatność.

Ponadto użytkownicy biura obsługi mogą nakładać ręczne wstrzymania z powodu oszustwa na zamówienia, które z jakiegoś powodu są podejrzane. Zamówienia mogą także być wstrzymywane automatycznie, jeśli spełniają aktywne kryteria i reguły decydujące o uznaniu za oszustwo. Aby uzyskać więcej informacji na temat tego rodzaju wstrzymania zamówienia, zobacz [Konfigurowanie alertów o oszustwie](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).

## <a name="viewing-and-managing-orders-that-are-on-hold"></a>Podgląd i zarządzanie wstrzymanymi zamówieniami

### <a name="viewing-hold-information-for-a-single-sales-order"></a>Wyświetlanie informacji o wstrzymaniu dla jednego zamówienia sprzedaży

Na stronie **Obsługa klienta** użytkownicy mogą wizualnie identyfikować wstrzymane zamówienia, ponieważ wiersze zamówienia są wyróżnione w określonym kolorze. Ten kolor jest definiowany za pomocą pola **Status wstrzymanego zamówienia sprzedaży** na stronie **Parametry modułu rozrachunków z odbiorcami**.

> [!NOTE]
> Jeśli wiersz jest zaznaczony na stronie, kolor wyróżnienia nie jest widoczny.

Użytkownicy mogą także wyświetlać informacje szczegółowe na temat zamówienia sprzedaży, aby dowiedzieć się, czy zamówienie jest wstrzymane. Szczegółowe informacje na temat stanu można uzyskać ze strony **Wszystkie zamówienia sprzedaży** lub **Obsługa klienta**. Jeśli zamówienie jest wstrzymane, ma ustawioną flagę **Nie przetwarzaj**, a pole **Szczegółowy stan** zawiera wartość **Wstrzymano** lub **Wstrzymanie z powodu oszustwa**, w zależności od scenariusza.

Aby wyświetlić szczegóły dotyczące wstrzymania pojedynczego zamówienia, użytkownicy mogą otworzyć szczegółowy widok strony **Wstrzymania zamówienia** ze strony **Obsługi klienta**, za pomocą **Opcji** menu dla wybranego zamówienia. Można również uzyskać dostęp do tego widoku ze strony **Wszystkie zamówienia sprzedaży**, wybierając elementu menu **Wstrzymanie zamówień** w zakładce **zamówienie sprzedaży**.

### <a name="viewing-all-orders-that-are-on-hold"></a>Podgląd wszystkich wstrzymanych zamówień

Aby wyświetlić wszystkie zamówienia, które zostały wstrzymane ręcznie lub automatycznie, przejdź do **Sprzedaży detalicznej i innej** \> **Odbiorców** \> **Wstrzymanie zamówień**.

Pulpit **Wstrzymania zamówień** zawiera widok listy wszystkich zamówień, które zostały wstrzymane z powodu działań ręcznych lub związanych z wykrywaniem oszustw. Wykorzystując standardowe opcje filtrowania i sortowania dostępne na stronie, użytkownicy mogą tworzyć widoki umożliwiające im wykonywanie operacji lub zarządzanie określonymi kodami wstrzymania, za których weryfikację odpowiadają. Pulpit **Wstrzymania zamówień** również wskazuje liczbę dni, przez jaką zamówienie jest wstrzymane. Informacje te mogą pomóc użytkownikom określać priorytety kolejki.

Aby uzyskać bardziej szczegółowy widok zamówień, które zostały wstrzymane, należy kliknąć opcję **Wstrzymanie zamówienia** w menu. Ten widok dostarcza informacje o odbiorcy, uwagi, które zostały dodane do zamówienia, odbiorcy lub wstrzymania działania. Widok dostarcza także informacje o przyczynie automatycznego wstrzymania, jeśli zamówienie zostało wstrzymane, ponieważ pasowało do reguły wykrywania oszustwa.

Zarówno w widoku listy, jak i widoku szczegółowym strony **Wstrzymania zamówień** użytkownicy mogą wyświetlać lub edytować dodatkowe informacje dotyczące zamówień, takie jak płatności, sumy i uwagi.

Opcje na karcie **Wyewidencjonowanie wstrzymanych** mogą być przydatne, jeśli wielu użytkowników w Twojej firmie pracuje jednocześnie nad kolejką wstrzymanych. Wybierając opcję **Wyewidencjonuj**, użytkownicy mogą wskazać, że pracują nad weryfikacją i analizą przyczyn wstrzymania zamówienia. Dzięki temu inni użytkownicy nie marnują czasu na wykonywanie tej samej pracy. W widoku szczegółowym strony **Wstrzymania zamówień** użytkownicy mogą wyświetlać informacje o dacie i godzinie wyewidencjonowania oraz o użytkowniku, który wyewidencjonował rekord wstrzymania.

Po wyewidencjonowaniu rekordu wstrzymania tylko użytkownik, który dokonał wyewidencjonowania, może wyczyścić wyewidencjonowanie. To ograniczenie ma na celu uniemożliwienie użytkownikom przejmowanie rekordów, nad którymi pracują już inni użytkownicy. Aby zwolnić zamówienie do kolejki, tak aby inni użytkownicy mogli nad nim pracować, użytkownik, który zaznaczył ten zapis musi zaznaczyć opcję **Wyczyść zaznaczenie**.

> [!NOTE]
> Wstrzymana płatność nie jest zwalniana, kiedy wyewidencjonowanie jest wyczyszczone.

W niektórych sytuacjach, na przykład gdy użytkownik jest chory lub przestał pracować w firmie, rekordy wyewidencjonowane dla tego użytkownika trzeba przypisać do innego użytkownika. Menedżer może zmienić przypisanie rekordów za pomocą opcji **Zastąp wyewidencjonowanie**.

## <a name="releasing-orders-that-are-on-hold"></a>Zwalnianie wstrzymanych zamówień

Zarówno w widoku listy, jak i widoku szczegółowym strony **Wstrzymania zamówień** karta **Wyczyść wstrzymanie** zawiera opcje używane do zwalniania wstrzymania zamówienia. Użyj opcji **Wyczyścić wstrzymania**, aby zwolnić zamówienie z wybranego kodu wstrzymania.

Zamówienia w biurze obsługi wymagają uregulowania płatności. W związku z tym wstrzymania nie można w pełni wyczyścić, jeśli płatność nie została zastosowana do zamówienia. Na stronie **Parametry biura obsługi** na karcie **Wstrzymania** upewnij się, że parametr **Prześlij po wyczyszczeniu** jest włączony. To ustawienie pozwala zagwarantować, że zaakceptowane zlecenie wstrzymania przejdzie przez poprawną logikę przesyłania, aby sprawdzić poprawność płatności i autoryzować je. W razie braku płatności użytkownik zobaczy informację o błędzie, a kod wstrzymania nie zostanie wyczyszczony.

Jeśli parametr **Prześlij po wyczyszczeniu** nie został ustawiony, użytkownicy powinni wybrać opcję **Usuń i prześlij** w menu **Wyczyść wstrzymanie** w celu zagwarantowania, że zamówienie przejdzie przez wszystkie wymagane weryfikacje płatności. Jeżeli przesyłanie zamówienia zakończy się niepowodzeniem, gdy w kanale biura obsługi jest włączona flaga **Włącz kończenie zamówienia**, zamówienie zostanie zwolnione ze stanu wstrzymania, ale flaga **Nie przetwarzaj** pozostanie ustawiona. Dlatego zamówienie nie jest zwalniane do magazynu do czasu zastosowania i sprawdzenia poprawności płatności.

Jeśli użytkownicy chcą usunąć wstrzymanie, ale wprowadzić dodatkowe zmiany w zamówieniu przed jego zwolnieniem do dalszego przetwarzania, mogą wybrać opcję **Usuń i modyfikuj**. Ta opcja powoduje usunięcie kodu wstrzymania i otwiera szczegóły zamówienia sprzedaży, tak aby użytkownicy mogli wprowadzić dodatkowe zmiany w zamówieniu. Użytkownicy mogą również zastosować płatność i przesłać zamówienie sprzedaży za pomocą logiki weryfikacji płatności, gdy włączona jest flaga **Włącz kończenie zamówienia** w kanale biura obsługi.

## <a name="reporting-options"></a>Opcje raportowania

Wybierz kolejno opcje **Handel detaliczny i inny** \> **Zapytania i raporty** \> **Raporty biura obsługi** \> **Raport wstrzymań zamówień**, aby uruchomić raport o wstrzymaniach zamówień według zakresów dat, kodów wstrzymania lub innych pokrewnych kryteriów.
