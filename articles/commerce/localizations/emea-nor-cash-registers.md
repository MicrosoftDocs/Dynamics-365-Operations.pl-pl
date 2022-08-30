---
title: Funkcje kasy dla Norwegii
description: Ten artykuł zawiera omówienie funkcjonalności kasy, która jest dostępna dla Norwegii w rozwiązaniu Microsoft Dynamics 365 Commerce, oraz wskazówki dotyczące konfigurowania jej.
author: EvgenyPopovMBS
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-10-31
ms.openlocfilehash: 30bd5ad8c1513c3d56cc4aa0a77b70fe38d31e0a
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346026"
---
# <a name="cash-register-functionality-for-norway"></a>Funkcje kasy dla Norwegii

[!include[banner](../includes/banner.md)]

Ten artykuł zawiera omówienie funkcjonalności kasy, która jest dostępna dla Norwegii w rozwiązaniu Dynamics 365 Commerce. Zawiera również wskazówki dotyczące konfigurowania tej funkcjonalności. Ta funkcjonalność składa się z następujących części:

- Wspólne funkcje punktu sprzedaży dostępne dla odbiorców we wszystkich krajach lub regionach. Przykłady obejmują opcję, za pomocą której można uniemożliwić wydrukowanie kopii paragonu więcej niż jeden raz.
- Funkcje specyficzne dla Norwegii, takie jak podpisy cyfrowe dla transakcji sprzedaży.

## <a name="overview-of-cash-register-functionality-for-norway"></a>Omówienie funkcjonalności kasy dla Norwegii

### <a name="common-pos-features"></a>Wspólne funkcje punktu sprzedaży

Aby dowiedzieć się więcej o funkcjach punktu sprzedaży dostępnych dla klientów we wszystkich krajach lub regionach, zobacz [Zasoby Pomocy dotyczące rozwiązania Dynamics 365 Retail](../index.md).

Wymienionych poniżej funkcji lokalizacji punktu sprzedaży, które zostały uprzednio zaimplementowane i udostępnione klientom we wszystkich krajach lub regionach, można teraz używać w sposób specyficzny dla Norwegii:

- **Drukowanie pól tekstowych na paragonie z użyciem czcionki o dużym rozmiarze.** Parametr **Rozmiar czcionki** w projektancie formatów paragonów umożliwia określenie, że dla pola w formacie paragonu ma być używany duży rozmiar czcionki. (Duży rozmiar czcionki jest około dwa razy większy od zwykłego rozmiaru czcionki). Tego parametru można użyć na przykład w celu wydrukowania wskaźnika „Kopia” z użyciem dużych znaków na kopii paragonu.
- **Rejestrowanie drukowania kopii paragonów w dzienniku zdarzeń inspekcji punktu sprzedaży.** Parametr **Inspekcja** w profilu funkcjonalności punktu sprzedaży umożliwia włączenie drukowania kopii paragonów oraz rejestrowanie innych zdarzeń inspekcji punktu sprzedaży. Zdarzenia inspekcji są rejestrowane w bazie danych kanału oraz w centrali. Zdarzenia inspekcji można wyświetlić na stronie **Zdarzenia inspekcji**.
- **Uniemożliwianie drukowania kopii paragonu więcej niż raz.** Gdy parametr **Inspekcja** jest włączony w profilu funkcjonalności punktu sprzedaży, uprawnienie punktu sprzedaży **Zezwalaj na drukowanie kopii paragonów** określa, czy jest możliwe drukowanie kopii paragonów. Dostępna jest także opcja, za pomocą której można uniemożliwić wydrukowanie kopii paragonu więcej niż jeden raz.

Ponadto dla Norwegii została zaimplementowana poniższa funkcja punktu sprzedaży, która była dostępna dla odbiorców ze wszystkich krajów lub regionów:

- **Zarejestruj dodatkowe zdarzenia w dzienniku zdarzeń inspekcji punktu sprzedaży.** Jeśli parametr **Inspekcja** będzie włączony w profilu funkcjonalności punktu sprzedaży, w dzienniku zdarzeń inspekcji punktu sprzedaży będą rejestrowane następujące zdarzenia:

    - Operacje sprawdzania ceny
    - Zastąpienia podatku
    - Korekty ilości w wierszach
    - Czyszczenie transakcji z bazy danych kanału

### <a name="norway-specific-pos-features"></a>Funkcje punktu sprzedaży specyficzne dla Norwegii

Wymienione poniżej specyficzne dla Norwegii funkcje punktu sprzedaży są włączone, gdy parametr **Kod ISO** w profilu funkcjonalności punktu sprzedaży ma wartość **Nie**.

#### <a name="digital-signing-of-sales-transactions"></a>Cyfrowe podpisywanie transakcji sprzedaży

Każda transakcja sprzedaży jest podpisywana cyfrowo. Podpis jest tworzony i rejestrowany w arkuszu transakcji punktu sprzedaży w momencie finalizacji transakcji. Podpis jest również dostępny w arkuszu eksportowanym na potrzeby inspekcji.

Podpisywane są tylko transakcje sprzedaży gotówkowej. Poniżej podano kilka przykładów transakcji, które są wykluczone z procesu podpisywania:

- Przedpłaty (wpłata na konto odbiorcy)
- Przedpłaty za zamówienia sprzedaży (wpłata za zamówienie odbiorcy)
- Wystawienie karty upominkowej
- Transakcje niesprzedażowe (przyjęcie do kasy, pobranie środków płatniczych itp.)

Podpisane dane to ciąg tekstowy zawierający wymienione poniżej pola danych. Pola danych są rozdzielane średnikami.

1. Poprzedni podpis dla tego samego punktu sprzedaży (dla pierwszej transakcji jest używana wartość zero \[**0**\]).
2. Data transakcji
3. Godzina transakcji
4. Numer sekwencyjny podpisanej transakcji
5. Kwota transakcji z podatkiem
6. Kwota transakcji bez podatku

W procesie podpisywania cyfrowego jest używany 1024-bitowy klucz RSA, dla którego jest używana funkcja wyznaczania wartości skrótu SHA-1 (RSA-SHA1-1024). Do podpisywania jest używany certyfikat zainstalowany w rozwiązaniu Commerce Scale Unit. Unikatowy identyfikator certyfikatu jest rejestrowany wraz z podpisem.

Podpis jest przechowywany w bazie danych sklepu i w bazie danych centrali wraz z danymi transakcji. Podpis transakcji wraz z danymi transakcji, które zostały użyte w celu wygenerowania tego podpisu, możesz wyświetlić na skróconej karcie **Transakcje fiskalne** na stronie **Transakcje sklepu**.

#### <a name="receipts"></a>Przychody

Paragony dla Norwegii mogą zawierać dodatkowe informacje, które zostały zaimplementowane przy użyciu pól niestandardowych:

- **Tytuł paragonu** — do układu formatu paragonu możesz dodać pole służące do identyfikowania typu paragonu. Na przykład paragon sprzedaży będzie zawierał tekst „Paragon sprzedaży”.
- **Numer sekwencyjny podpisanej transakcji** — na paragonie może być widoczny numer sekwencyjny podpisanej transakcji, który umożliwia skojarzenie wydrukowanego paragonu z podpisem cyfrowym w bazie danych.
- **Sumy paragonów** — niestandardowe pola sum paragonów umożliwiają wykluczanie kwot niezwiązanych ze sprzedażą z łącznych kwot transakcji. Kwoty niezwiązane ze sprzedażą obejmują kwoty z następujących operacji:

    - Przedpłaty (wpłata na konto odbiorcy)
    - Przedpłaty za zamówienia sprzedaży (wpłata za zamówienie odbiorcy)
    - Wystawienie karty upominkowej
    - Dodawanie funduszy do karty upominkowej

#### <a name="x-and-z-reports"></a>Częściowe i końcowe raporty sprzedaży

Informacje umieszczane w częściowych i końcowych raportach sprzedaży są wybierane na podstawie wymagań norweskich. Na przykład kwoty w polu **Sprzedaż gotówkowa — suma** zawierają tylko kwoty transakcji sprzedaży gotówkowej i nie obejmują operacji wystawiania kart upominkowych ani przedpłat. Wartość Sprzedaż gotówkowa — suma jest również podawana dla grupy towarów i metody płatności. Ponadto są zachowywane i drukowane łączne kwoty **Suma końcowa sprzedaży** i **Suma końcowa zwrotów**.

#### <a name="saf-t-cash-register-audit-file"></a>Plik inspekcji kasy SAF-T

Możesz wyeksportować arkusz transakcji w punkcie sprzedaży we wstępnie zdefiniowanym formacie standardowego pliku inspekcji Standard Audit File — Tax (SAF-T). Plik inspekcji zawiera informacje dotyczące organizacji, odpowiednie dane główne (takie jak grupy towarów, towary i kody podatków), dane transakcji sprzedaży gotówkowej wraz z podpisami tych transakcji, dane zdarzeń niezwiązanych ze sprzedażą oraz dane raportu na koniec dnia.

Plik inspekcji można wyeksportować w następujących scenariuszach:

- Pojedynczy sklep
- Wszystkie sklepy
- Pojedynczy terminal
- Wszystkie terminale

Możesz także wysłać raport z jednej osoby prawnej w imieniu innej osoby prawnej. W tym przypadku musisz uruchomić eksport z operacyjnej osoby prawnej i określić raportującą osobę prawną jako nadawcę raportu.

Format kasy SAF-T jest implementowany na poziomie centrali przy użyciu funkcji [Raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md). 

## <a name="setting-up-commerce-for-norway"></a>Konfigurowanie rozwiązania Commerce dla Norwegii

W tej sekcji opisano ustawienia specyficzne oraz zalecane dla Norwegii. Aby uzyskać więcej informacji, zobacz [Zasoby Pomocy dotyczące rozwiązania Dynamics 365 Retail](../index.md).

Aby móc używać funkcjonalności specyficznej dla Norwegii, musisz wykonać poniższe zadania:

- W podstawowym adresie osoby prawnej ustaw w polu **Kraj/region** wartość **NOR** (Norwegia).
- W profilu funkcjonalności punktu sprzedaży każdego sklepu zlokalizowanego w Norwegii ustaw w polu **Kod ISO** wartość **NO** (Norwegia).

Musisz także określić wymienione poniżej ustawienia dla Norwegii.

### <a name="enable-features-for-norway"></a>Włącz funkcje dla Norwegii

W obszarze roboczym **Zarządzanie funkcjami** należy włączyć następujące funkcje centrali Commerce headquarters:

- (Norwegia) Włącz dodatkowe zdarzenia inspekcji w punkcie sprzedaży
- (Norwegia) Włączanie dodatkowych informacji w zestawieniach na koniec dnia w punkcie sprzedaży

### <a name="set-up-the-legal-entity"></a>Konfigurowanie osoby prawnej

Upewnij się, że określono nazwę osoby prawnej. Ta nazwa będzie drukowana w częściowych i końcowych raportach sprzedaży.

Ponadto określ numer organizacji w polu **Numer rozliczeniowy** na skróconej karcie **Informacje o koncie bankowym**.

### <a name="set-up-value-added-tax-vat-per-norwegian-requirements"></a>Konfigurowanie podatku VAT zgodnie z wymaganiami norweskimi


Musisz utworzyć kody podatków, grupy podatków oraz grupy podatków dla towarów. Musisz także skonfigurować informacje o podatkach dla produktów i usług. Aby uzyskać więcej informacji dotyczących sposobu konfigurowania i używania podatku, zobacz [Omówienie podatku](../../finance/general-ledger/indirect-taxes-overview.md).

Musisz także określić grupy podatków i włączyć opcję **Ceny zawierają podatek** dla sklepów zlokalizowanych w Norwegii.

### <a name="set-up-functionality-profiles"></a>Konfigurowanie profilów funkcjonalności

Musisz włączyć inspekcję i skonfigurować numerowanie paragonów.

### <a name="update-pos-permissions-groups-and-individual-permission-settings-for-store-workers"></a>Aktualizowanie ustawień grup uprawnień i pojedynczych uprawnień w punkcie sprzedaży dla pracowników sklepu

Ustaw odpowiednią wartość uprawnienia **Zezwalaj na drukowanie kopii paragonów**:

- **Zawsze zezwalaj** — operator może wielokrotnie wydrukować kopię paragonu.
- **Zezwalaj tylko raz** — operator może wydrukować kopię paragonu tylko raz.
- **Zezwalaj tylko raz i tylko jeśli jest dostępna baza danych centrali (HQ DB)** — operator może wydrukować kopię paragonu tylko raz, jeśli baza danych centrali jest dostępna za pośrednictwem usługi Commerce Data Exchange: Real-time Service, co umożliwia systemowi potwierdzenie, że w żadnym sklepie nie wydrukowano uprzednio kopii danego paragonu.
- **Nigdy** — operator nie może wydrukować kopii paragonu.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Konfigurowanie pól niestandardowych, aby można było ich używać w formatach paragonów dla paragonów sprzedaży

Na stronie **Tekst w języku** dodaj wymienione poniżej rekordy dla etykiet pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora języka**, **Identyfikatora tekstu** i **Tekst** przedstawione w poniższej tabeli są tylko przykładami. Można je zmienić, aby spełniały wymagania użytkownika.

| Identyfikator języka | Tekst                   | Identyfikator tekstu |
|-------------|------------------------|---------|
| pl       | Tytuł paragonu          | 900011  |
| en-US       | Jest kartą upominkową           | 900012  |
| en-US       | Suma (sprzedaż)          | 900013  |
| en-US       | Suma podatku (sprzedaż)      | 900014  |
| en-US       | Suma z podatkiem (sprzedaż) | 900015  |
| en-US       | Kwota podatku (sprzedaż)     | 900016  |
| en-US       | Identyfikator transakcji gotówkowej    | 900017  |

Na stronie **Pola niestandardowe** dodaj następujące rekordy dla pól niestandardowych używanych w układach paragonów. Pamiętaj, że wartości **Identyfikatora tekstu podpisu** muszą być zgodne z wartościami **Identyfikatora tekstu** określonymi na stronie **Tekst w danym języku**.

| Nazwa                            | Typ    | Identyfikator tekstu podpisu |
|---------------------------------|---------|-----------------|
| ReceiptTitle                    | Pokwitowanie | 900011          |
| IsGiftCard                      | Pokwitowanie | 900012          |
| SalesTotalExt                   | Pokwitowanie | 900013          |
| TaxTotalExt                     | Pokwitowanie | 900014          |
| TotalWithTaxExt                 | Pokwitowanie | 900015          |
| AmountPerTaxExt                 | Pokwitowanie | 900016          |
| CashTransactionSequentialNumber | Pokwitowanie | 900017          |

> [!NOTE]
> Ważne jest, aby określić poprawne nazwy pól niestandardowych, tak jak podano w tabeli powyżej. Niepoprawna nazwa pola niestandardowego spowoduje brak danych na paragonach.

### <a name="configure-receipt-formats"></a>Konfigurowanie formatów paragonów

Dla wszystkich wymaganych formatów paragonów zmień wartość pola **Zachowanie drukowania** na **Zawsze drukuj** dla danego formatu paragonu.

W projektancie formatów paragonów dodaj wymienione poniżej pola niestandardowe do odpowiednich sekcji paragonu. Pamiętaj, że nazwy pól muszą odpowiadać tekstom w języku zdefiniowanym w poprzedniej sekcji.

1. Nagłówek:

    - **Tytuł paragonu** — to pole określa typ paragonu.
    - **Identyfikator transakcji kasowej** — w tym polu jest drukowany numer sekwencyjny podpisanej transakcji kasowej.

2. Wiersze:

    - **Jest kartą upominkową** — to pole oznacza wiersz paragonu jako powiązany z operacją Wystaw kartę upominkową lub Dodaj do karty upominkowej.

3. Stopka:

    - **Suma (sprzedaż)** — w tym polu jest drukowana łączna kwota sprzedaży gotówkowej objętej paragonem. Kwota bez podatku. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
    - **Suma podatku (sprzedaż)** — w tym polu jest drukowana łączna kwota podatku dla sprzedaży gotówkowej. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
    - **Suma z podatkiem (sprzedaż)** — w tym polu jest drukowana łączna kwota sprzedaży gotówkowej objętej paragonem. Kwota zawiera podatek. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.
    - **Kwota podatku (sprzedaż)** — w tym polu jest drukowana kwota podatku dla sprzedaży gotówkowej odpowiadająca kodowi podatku. Przedpłaty i operacje związane z kartami upominkowymi są wykluczane.

Aby uzyskać więcej informacji o sposobie pracy z formatami paragonów, zobacz [Konfigurowanie i projektowanie formatów paragonów](../receipt-templates-printing.md).

### <a name="configure-the-saf-t-cash-register-export-format"></a>Konfigurowanie formatu eksportu kasy SAF-T

Konfiguracja kasy SAF-T jest dostępna do pobrania z usługi Microsoft Dynamics Lifecycle Services (LCS). Aby uzyskać więcej informacji, zobacz [Importowanie konfiguracji raportowania elektronicznego](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-import-ger-configurations.md). Musisz pobrać następujące konfiguracje:

- **Dane kanału sprzedaży detalicznej (wersja 1)** — konfiguracja modelu danych.
- **Dane kanału sprzedaży detalicznej DMM (wersja 1.14)** — konfiguracja mapowania modelu danych.
- **Kasa NO SAF T (wersja 1.20)** — konfiguracja formatu.

Po zaimportowaniu konfiguracji na stronie **Parametry rozwiązania Commerce** na karcie **Dokumenty elektroniczne** w polu **Format eksportu kasy SAF-T** wybierz nazwę zaimportowanej konfiguracji formatu.

Musisz także zamapować wymagane dane główne na wstępnie zdefiniowane kody standardu SAF-T. Aby uzyskać więcej informacji, zobacz dokumentację kasy SAF-T dostarczoną przez norweski urząd skarbowy. Aby utworzyć mapowanie, musisz ustawić nowe pole **Kod kasy SAF-T** na następujących stronach:

- Grupy pozycji
- Formy płatności
- Kody podatków

### <a name="configure-channel-components"></a>Konfiguracja składników kanału.

Aby włączyć funkcjonalność specyficzną dla Norwegii, musisz skonfigurować składniki kanału. Aby uzyskać więcej informacji, zobacz [Wskazówki dotyczące wdrażania](emea-nor-fi-deployment.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
