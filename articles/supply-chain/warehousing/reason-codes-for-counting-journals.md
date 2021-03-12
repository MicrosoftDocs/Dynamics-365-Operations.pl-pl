---
title: Kody przyczyn zliczania zapasów
description: W tym temacie opisano sposób konfigurowania i stosowania kodów przyczyn dla zadań inwentaryzacji.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 66e1fb9f32aa31221f85180339b8b6ee55836be1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996155"
---
# <a name="reason-codes-for-inventory-counting"></a>Kody przyczyn zliczania zapasów

[!include [banner](../includes/banner.md)]

Kody przyczyn umożliwiają analizowanie wyników procesu inwentaryzacji (zliczania) i wszelkich rozbieżności pojawiających się w trakcie tego procesu. Można określić przyczynę wykonywania inwentaryzacji, taką jak uszkodzenie palety lub korekta zapasów oparta na próbkach zapasów.

## <a name="recommendation"></a>Rekomendacja

Przed skonfigurowaniem systemu zalecamy zdefiniowanie strategii pracy z kodami przyczyn. Na przykład spróbuj odpowiedzieć na następujące pytania:

- Czy kody przyczyn powinny być wymagane w magazynach?
- Czy kody przyczyn powinny być obowiązkowe, czy też dla niektórych towarów opcjonalne?
- Ile kodów przyczyn potrzeba?
- Jak kody przyczyn powinny być wykorzystywane przez osoby używające skanerów kodów kreskowych? Czy kody przyczyn powinny być wstępnie wybierane, obowiązkowe i nieedytowalne?
- Czy pracownicy magazynu potrzebują innego zachowania kodów przyczyn w przenośnych skanerach? Jeśli odpowiedź brzmi „tak”, można utworzyć więcej elementów menu i przypisać je do różnych osób.

## <a name="where-reason-codes-apply"></a>Gdzie stosuje się kody przyczyn

Można utworzyć wiele zasad kodów przyczyn, a każda zasada kodu przyczyny może mieć dwie zasady kodów przyczyn zliczania. Zasady kodów przyczyn zliczania mogą być używane na poziomie magazynu lub towaru.

## <a name="set-up-reason-code-policies"></a>Konfigurowanie zasad kodów przyczyn zliczania

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Zapasy** \> **Zasady kodów przyczyn zliczania** i utwórz nową zasadę kodu przyczyny.
2. W polu **Typ kodu przyczyny zliczania** wybierz opcję **Wymagane** lub **Opcjonalne**, aby określić, czy wybór kodu przyczyny powinien być działaniem obowiązkowym czy opcjonalnym w jednym z następujących arkuszy inwentaryzacyjnych:

    - Inwentaryzacja ciągła (za pomocą urządzenia przenośnego)
    - Inwentaryzacja punktowa (za pomocą urządzenia przenośnego)
    - Inwentaryzacja progowa (za pomocą urządzenia przenośnego)
    - Korekta wewnętrzna (za pomocą urządzenia przenośnego)
    - Korekta zewnętrzna (za pomocą urządzenia przenośnego)
    - Arkusz inwentaryzacyjny (za pomocą pełnego klienta)

Można również skonfigurować kody przyczyn dla poszczególnych magazynów i produktów. Konfiguracja kodów przyczyn produktów może nie brać pod uwagę konfiguracji dla magazynów.

## <a name="mandatory-reason-codes"></a>Obowiązkowe kody przyczyn

Jeśli parametr **Wymagane** jest ustawiony w konfiguracji kodów przyczyn dla magazynów lub towarów, arkusz inwentaryzacyjny można sfinalizować i zamknąć dopiero po podaniu kodu przyczyny.

### <a name="set-up-reason-codes-for-warehouses"></a>Konfigurowanie kodów przyczyn dla magazynów

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Ustawienia** \> **Podział magazynu** \> **Magazyny**.
2. Na karcie **Magazyn** w polu **Zasada kodów przyczyn zliczania** wybierz jedną z następujących opcji:

    - **Puste** — parametr skonfigurowany dla towaru jest używany do ustalania, czy arkusze inwentaryzacyjne są wymagane dla produktu.
    - **Wymagane** — kod przyczyny jest zawsze wymagany w arkuszach inwentaryzacyjnych dla magazynu.
    - **Opcjonalnie** — kod przyczyny nie jest wymagany w arkuszach inwentaryzacyjnych dla magazynu.

### <a name="set-up-reason-codes-for-products"></a>Konfigurowanie kodów przyczyn dla produktów

1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** \> **Produkty** \> **Zwolnione produkty**.
2. Na karcie **Produkt** wybierz opcję **Zasada kodów przyczyn zliczania**, a następnie wybierz jedną z następujących opcji:

    - **Puste** — parametr skonfigurowany dla magazynu jest używany do ustalania, czy arkusze inwentaryzacyjne są wymagane dla produktu.
    - **Wymagane** — kod przyczyny jest zawsze wymagany w arkuszach inwentaryzacyjnych dla produktu. To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.
    - **Opcjonalnie** — kod przyczyny nie jest wymagany w arkuszach inwentaryzacyjnych dla produktu. To ustawienie zastępuje wszelkie ustawienia kodów przyczyn na poziomie magazynu.

### <a name="use-reason-codes-in-counting-journals"></a>Używanie kodów przyczyn w arkuszach inwentaryzacyjnych

W arkuszu inwentaryzacyjnym można dodawać kody przyczyn dla następujących typów inwentaryzacji:

- Inwentaryzacja ciągła
- Inwentaryzacja punktowa
- Inwentaryzacja progowa
- Korekta wewnętrzna
- Korekta zewnętrzna

Kody przyczyn są dodawane do wierszy arkusza w arkuszach inwentaryzacyjnych typu **Arkusz zliczania**.

1. Wybierz kolejno opcje **Zarządzanie zapasami** \> **Wpisy w arkuszu** \> **Zliczanie pozycji** \> **Inwentaryzacja**.
2. W wierszu szczegółów arkusza inwentaryzacyjnego w polu **Kod przyczyny zliczania** wybierz opcję.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>Wyświetlanie historii inwentaryzacji zarejestrowanej według kodów przyczyn

- Wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Historia inwentaryzacji**, a następnie w polu **Kod przyczyny zliczania** obejrzyj historię inwentaryzacji zarejestrowaną za pomocą kodu przyczyny.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Używanie kodu przyczyny do korygowania ilości

1. Na stronie **Dostępne zapasy** wybierz opcję **Korekta ilości**. Stronę **Dostępne zapasy** można otworzyć na kilka sposobów. Na przykład wybierz kolejno opcje **Zarządzanie zapasami** \> **Zapytania i raporty** \> **Dostępne zapasy**.
2. Wybierz opcję **Korekta ilości**, a następnie w polu **Kod przyczyny zliczania** wybierz kod przyczyny.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Konfigurowanie kodów przyczyn dla elementów menu na urządzeniu przenośnym

Kody przyczyn można skonfigurować dla każdego typu inwentaryzacji obsługiwanego za pomocą elementu menu na urządzeniu przenośnym. Konfiguracja pozycji menu dla urządzenia przenośnego zawiera następujące informacje:

- Czy kod przyczyny jest widoczny dla pracownika korzystającego z urządzenia przenośnego podczas inwentaryzacji.
- Domyślny kod przyczyny wyświetlany w elemencie menu na urządzeniu przenośnym.
- Czy użytkownik może edytować kod przyczyny.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Konfigurowanie kodów przyczyn na urządzeniu przenośnym

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.
2. Na karcie **Inwentaryzacja ciągła** wybierz opcję **Inwentaryzacja ciągła**.
3. W polu **Domyślny kod przyczyny zliczania** ustaw domyślny kod przyczyny, który ma być rejestrowany podczas inwentaryzacji za pomocą elementu menu na urządzeniu przenośnym.
4. W polu **Wyświetl kod przyczyny zliczania** wybierz opcję **Wiersz**, aby był pokazywany kod przyczyny po zarejestrowaniu każdego odchylenia. Alternatywnie wybierz opcję **Ukryj**, jeśli kod przyczyny nie powinien być wyświetlany.
5. W opcji **Edytuj kod przyczyny zliczania** ustaw wartość **Tak** lub **Nie**. Jeśli ustawisz wartość **Tak**, pracownik może edytować kod przyczyny wyświetlony na urządzeniu przenośnym podczas inwentaryzacji.

> [!NOTE]
> Przycisk **Inwentaryzacja ciągła** można włączyć dla każdego elementu menu na urządzeniu przenośnym służącym do wykonywania inwentaryzacji. Przykładem są elementy menu dla inwentaryzacji punktowych, pracy sterowanej przez użytkownika i pracy sterowanej przez system.

## <a name="cycle-count-approvals"></a>Zatwierdzenia inwentaryzacji ciągłej

Przed zatwierdzeniem inwentaryzacji użytkownik może zmienić kod przyczyny skojarzony z inwentaryzacją. Po zatwierdzeniu inwentaryzacji kod przyczyny jest wprowadzany w wierszach arkusza inwentaryzacyjnego.

### <a name="modify-cycle-count-approvals"></a>Modyfikowanie zatwierdzeń inwentaryzacji ciągłej

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Inwentaryzacja ciągła** \> **Praca inwentaryzacji ciągłej oczekuje na przegląd**.
2. Wybierz opcję **Inwentaryzacja ciągła**, a następnie w polu **Kod przyczyny** wybierz nowy kod przyczyny.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>Modyfikowanie elementu menu na urządzeniu przenośnym dla korekty wewnętrznej i zewnętrznej

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**, a następnie wybierz opcję **Korekta wewnętrzna i zewnętrzna**.
2. W opcji **Użyj istniejącej pracy** ustaw wartość **Nie**.
3. W polu **Proces tworzenia pracy** wybierz opcję **Korekta wewnętrzna**.

Następujące pola zostaną dodane do elementu menu na urządzeniu przenośnym po wybraniu opcji **Korekta wewnętrzna** lub **Korekta zewnętrzna** w trakcie procesu tworzenia pracy:

- Domyślny kod przyczyny zliczania
- Wyświetl kod przyczyny zliczania
- Edytuj kod przyczyny zliczania
