---
title: Konfigurowanie buforów zapasów i poziomów zapasów
description: W tym temacie wyjaśniono, jak skonfigurować bufory zapasów i poziomy zapasów, które decydują o dostępności zapasów w witrynach Microsoft Dynamics 365 Commerce.
author: boycezhu
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: ef58dbb756c7bed3924010cb33eff27af66cd0bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414969"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Konfigurowanie buforów zapasów i poziomów zapasów

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak skonfigurować bufory zapasów i poziomy zapasów, które decydują o wiadomościach o dostępności zapasów w witrynach Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

W Dynamics 365 Commerce w centrali przechowywane są dane magazynowe i różne kanały, takie jak aplikacje punkt sprzedaży (POS), magazyny handlu elektronicznego i inne zintegrowane aplikacje, które w sposób asynchroniczny ściągają i wypychanie. Dlatego dostępne wartości zapasów, które są uzyskiwane za pośrednictwem strony zapasów w Commerce headquarters, interfejsu użytkownika POS (UI) oraz interfejsów API dostępności zapasów e-Commerce, nie zawsze są w 100% dokładne w czasie rzeczywistym.

Zamiast wyświetlać rzeczywiste wartości zapasów w sklepach e-Commerce, wiele sprzedawców preferuje wyświetlanie komunikatów o stanie dostępności zapasów (na przykład „dostępne” lub „wyprzedane”), aby poinformować odbiorców, czy dany towar jest dostępny do zakupionych lub potencjalnie nieaktywnych zapasów. W tym celu bufory magazynowe i poziomy zapasów, które ustalają obsługę wiadomości o dostępności zapasów, muszą zostać udostępnione i skonfigurowane.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Wymaganie wstępne: Włącz bufory zapasów i funkcję poziomów zapasów

Funkcje buforów magazynowych i poziomów zapasów są kontrolowane przez funkcję zarządzania funkcjami w Commerce headquarters. Aby włączyć funkcję, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Administrator systemu** \> **Obszary robocze** \> **Zarządzanie funkcjami**.
1. Wyszukaj funkcję **Włącz bufory zapasów i poziomy zapasów**, wybierz jej wiersz, a następnie wybierz pozycję **Włącz teraz**.

Po włączeniu tej funkcji można odszukać poziomy zapasów w **Retail i Commerce \> Zarządzanie zapasami**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Tworzenie i Konfigurowanie profilu na poziomie zapasów

*Profil poziomu zapasów* określa, czy dany stan ilości produktów jest brany pod uwagę w magazynie, poza magazynem czy też w innym stanie niestandardowym. Dla każdej firmy można utworzyć i skonfigurować wiele profilów poziomu zapasów. Każdy profil składa się z zbioru poziomów zapasów, a każdy poziom jest definiowany za pomocą *zakresu*, *kodu* i *etykiety*.

- **Zakres** — każdy zakres jest definiowany za pomocą *ilości początkowej* i *ilości końcowej*. Wartość ilości mieści się w zakresie, który jest większy niż ilość początkowa tego zakresu i nie jest większy niż ilość końcowa.
- **Kod** — kod jest wewnętrznym skrótem reprezentującym poziom. Klienci, którzy bezpośrednio integrują się z interfejsami API zapasów, mogą wykorzystywać kody do tworzenia dodatkowej logiki dla danego poziomu zapasów. Na przykład można wyłączyć możliwość zakupu produktu, gdy jego kod poziomu zapasów to **OOS** („wyprzedano”).
- **Etykieta** — etykieta to zrozumiała wiadomość dla odbiorcy, która umożliwia odbiorcom poziom zapasów w witrynie e-Commerce.

### <a name="create-an-inventory-level-profile"></a>Tworzenie profilu na poziomie zapasów

Aby utworzyć profil poziomu zapasów, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce** \> **Zarządzanie zapasami** \> **Poziomy zapasów**.
1. W okienku akcji wybierz opcję **Nowy**, a następnie wprowadź wartości w polach **Identyfikator profilu** i **Opis**.
1. Na skróconej karcie **Zakresy** wybierz pozycję **Dodaj**, aby dodać nowy poziom, a następnie wprowadź wartości w kolumnach **ilość początkowa**, **ilość końcowa**, **kod** i **etykieta** dla tego poziomu. Powtórz ten krok, aby dodać więcej poziomów. W razie konieczności można edytować wartości w siatce danych lub wybrać opcję **Usuń**, aby usunąć poziom.
1. Na okienku akcji wybierz opcję **Zapisz**.

Podczas tworzenia nowego profilu automatycznie inicjowane są dwa poziomy zapasów:

- **OOS** — poziom „wyprzedano”, gdzie dolna granica zakresu jest ujemna. Nie można edytować ilości początkowej i kodu dla tego poziomu.
- **AVAIL** — poziom „dostępny”, gdzie górna granica zakresu jest nieskończona. Nie można edytować ilości końcowej i kodu dla tego poziomu.

> [!NOTE]
> Między zakresami w definicji profilu nie może być przerw lub nakładać się.

W celu skonfigurowania zlokalizowanych ciągów dla komunikatu etykiety można skorzystać z przycisku **Tłumaczenia** w okienku akcji. Następnie należy uruchomićzadanie harmonogramu dystrybucji **1110** (**Konfiguracja globalna**) w celu zsynchronizowania zlokalizowanych ciągów z kanałami.

### <a name="configure-an-inventory-level-profile"></a>Konfiguracja profilu na poziomie zapasów

Profil na poziomie zapasów można skonfigurować na poziomie kategorii produktu lub na poziomie poszczególnych produktów. W przypadku skonfigurowania profilu poziomu zapasów dla produktu poziom zapasów jest określany na podstawie zakresów zdefiniowanych w połączonym profilu. W przeciwnym razie poziom zapasów „dostępny” lub „wyprzedano” jest określany na podstawie tego, czy produkt ma dodatnią ilość dostępnych zapasów.

Aby skonfigurować profil poziomu zapasów dla kategorii, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce** \> **Produkty i kategorie** \> **Hierarchia produktów Commerce**.
1. Wybierz kategorię, dla której chcesz skonfigurować profil poziomu zapasów.
1. Na skróconej karcie **Właściwości sprzedaży** wybierz firmę.
1. W sekcji **Zapasy Commerce** w polu **Profil poziomu zapasów** wybierz jeden ze wstępnie zdefiniowanych profilów poziomu zapasów.

Przycisk **Aktualizuj produkty** w okienku akcji służy do propagowania wartości profilu na poziomie kategorii do produktów podstawowych kategorii. Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie kategoriami produktów i produktami](category-management-product-creation.md).

Aby skonfigurować profil poziomu zapasów dla wydanego produktu, wykonaj następujące kroki.

1. Wybierz kolejno opcje Handel detaliczny i inny **Retail i Commerce** \> **Produkty i kategorie** \> **Zwolnione produkty według kategorii**.
1. Wybierz produkt, a następnie otwórz stronę szczegółów produktu.
1. Na skróconej karcie **Sprzedaż** sekcji **Zapasy Commerce** w polu **Profil poziomu zapasów** wybierz jeden ze wstępnie zdefiniowanych profilów poziomu zapasów.

Podczas tworzenia nowego produktu pole **Profil poziomu zapasów**, podobnie jak wiele innych atrybutów na poziomie produktu, będzie mieć ustawioną wartość skonfigurowaną dla kategorii, z którą jest skojarzony produkt.

> [!NOTE]
> Profil poziomu zapasów jest atrybutem charakterystycznym dla firmy. W przypadku tej samej kategorii lub produktu wartość profilu na poziomie zapasów może być różna w różnych firmach.

Aby zsynchronizować konfiguracje profili poziomów zapasów ze kanałami, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Dane IT sprzedaży** \> **Harmonogram dystrybucji**.
1. Uruchom harmonogram dystrybucji **1040** (**Produkt**).

## <a name="configure-an-inventory-buffer"></a>Konfigurowanie buforu zapasów

*Bufor zapasów* to zdefiniowana przez użytkownika wartość, która odejmuje dodatkową ilość towaru od ilości oryginalnej w celu obliczenia szacowanej ilości. Ta Szacowana ilość pozwala detalistom na bezpieczny bufor w taki sposób, aby nie dokonywać sprzedaży produktu przez sprzedanie więcej niż jego faktyczne dostępne zapasy. Profil na poziomie zapasów można skonfigurować bufor zapasów na poziomie kategorii produktu lub na poziomie poszczególnych produktów. Jeśli nie określono bufora zapasów, używany jest domyślna wartość **0** (zero).

Aby skonfigurować bufor zapasów dla kategorii, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Retail i Commerce** \> **Produkty i kategorie** \> **Hierarchia produktów Commerce**.
1. Wybierz kategorię, dla której chcesz skonfigurować bufor zapasów.
1. Na skróconej karcie **Właściwości sprzedaży** wybierz firmę.
1. W sekcji **Zapasy Commerce** w polu **Bufor zapasów** wprowadź wartość dodatnią.

Przycisk **Aktualizuj produkty** w okienku akcji służy do propagowania wartości bufora na poziomie kategorii do produktów podstawowych kategorii. Aby uzyskać więcej informacji, zajrzyj do [Zarządzanie kategoriami produktów i produktami](category-management-product-creation.md).

Aby skonfigurować bufor zapasów dla wydanego produktu, wykonaj następujące kroki.

1. Wybierz kolejno opcje Handel detaliczny i inny **Retail i Commerce** \> **Produkty i kategorie** \> **Zwolnione produkty według kategorii**.
1. Wybierz produkt, a następnie otwórz stronę szczegółów produktu.
1. Na skróconej karcie **Sprzedaż** w sekcji **Zapasy Commerce** w polu **Bufor zapasów** wprowadź wartość dodatnią.

Podczas tworzenia nowego produktu pole **Bufor zapasów** będzie mieć ustawioną wartość skonfigurowaną dla kategorii, z którą jest skojarzony produkt.

> [!NOTE]
> Jeśli dla danego produktu skonfigurowano profile buforów zapasów i poziomów zapasów, Szacowana ilość produktu (to znaczy ilość oryginalna pomniejszona o wartość buforu) będzie używana do obliczania zakresu w celu określenia poziomu zapasów.

Aby zsynchronizować konfiguracje bufora zapasów z kanałami, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny** \> **Dane IT sprzedaży** \> **Harmonogram dystrybucji**.
1. Uruchom harmonogram dystrybucji **1040** (**Produkt**).

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Używanie buforów zapasów i poziomów zapasów w scenariuszu handlu elektronicznego

Funkcja kreatora witryn Commerce korzysta z buforów zapasów i funkcji poziomu zapasów w programie Commerce Headquarter, aby określić obsługę zapasów w ramach witryn handlu elektronicznego. Aby uzyskać więcej informacji, zobacz [Zastosuj ustawienia zapasów](inventory-settings.md).

Alternatywnie, jeśli zintegrujesz się z zewnętrznym rozwiązaniem e-commerce, możesz użyć interfejsów API **GetEstimatedAvailability** i **GetEstimatedProductWarehouseAvailability**, aby pokazać dostępność zapasów dla produktu w Twoim scenariuszu e-Commerce. Aby uzyskać więcej informacji o tych interfejsach API, zapoznaj się z tematem [Oblicz dostępność zapasów dla kanałów sieci sprzedaży](calculated-inventory-retail-channels.md).

Wprowadzenie buforów zapasów i poziomów zapasów umożliwia tym interfejsom API zwracanie kodów poziomu zapasów i etykietowanie komunikatów, które są określane na podstawie całkowitej dostępnej i dostępnej wartości fizycznej. Interfejsy API można następnie skonfigurować w celu określenia, czy ilość zapasów jest zwracana razem z wiadomością, oraz czy dostępna ilość jest zmniejszana o wartość bufora zapasów.

Aby skonfigurować odpowiedź interfejsów API dostępności produktu, wykonaj następujące kroki.

1. Wybierz kolejno **Retail i commerce** \> **Ustawienia centrali** \> **Parametry** \> **Parametry Commerce**.
1. W sekcji **Magazyn sklepu**, na karcie **Zapasy**, w polu **Interfejsy API dostępności produktów dla handlu elektronicznego** wybierz wartość.
1. Aby zastosować ustawienia do kanałów, uruchom zadanie harmonogramu dystrybucji **1110** (**Konfiguracja globalna**).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie kategoriami produktów i produktami](category-management-product-creation.md)

[Zastosuj ustawienia zapasów](inventory-settings.md)

[Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]