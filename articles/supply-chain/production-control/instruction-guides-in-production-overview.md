---
title: Udostępnianie przewodników po rzeczywistości mieszanej pracownikom produkcji
description: W tym temacie opisano sposób integrowania modułu zarządzania produkcją w systemie Microsoft Dynamics 365 Supply Chain Management z Dynamics 365 Guides.
author: johanhoffmann
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "61943"
- intro-internal
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 703f2cb9a1ea8691420765a8598d59f3e6cc6488
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062959"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Udostępnianie przewodników po rzeczywistości mieszanej pracownikom produkcji

[!include [banner](../includes/banner.md)]


Pracownicy w procesach produkcyjnych będą korzystać z odpowiednich instrukcji, które są dostępne w odpowiednim czasie w kontekście ich pracy. *Instrukcje* dotyczą kilku typów pracy, w tym: montażu, usług, operacji, certyfikacji i bezpieczeństwa. We wszystkich tych podstawowych funkcjach biznesowych, instrukcje ciągłego szkolenia mogą pomóc pracownikom zrobić więcej i pracować lepiej.

## <a name="introduction"></a>Wprowadzenie

Instrukcje można udostępniać na różne sposoby. Jeden skuteczny system, który jest dostarczany jako gotowy, wykorzystuje system [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

Dynamics 365 Guides umożliwia szkolenie pracowników za pomocą praktycznych kursów. Standardowe procesy można definiować, stosując instrukcje krok po kroku, które nauczą pracownikom korzystania z wymaganych narzędzi i części oraz pokażą pracowników, jak używać tych narzędzi podczas pracy.

Można dołączać przewodniki do różnych aspektów kontroli produkcji, w tym:

- [Zasoby](#resources)
- [Grupy zasobów](#resource-groups)
- [Zwolnione produkty](#released-products)
- [Formuły](#formulas)
- [Wersje formuły](#formula-versions)
- [List składowych (BOM)](#bom)
- [Wersji BOM](#bom-versions)
- [Marszruty](#routes)
- [Wersje marszruty](#route-versions)
- [Relacji operacji marszrut](#route-operation-relations)

> [!NOTE]
> Można także dołączać przewodniki do zarządzania środkami trwałymi. Aby uzyskać więcej informacji o opcji, zobacz temat [Integracja Dynamics 365 Supply Chain Management (zarządzanie składnikami majątku) z Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

Jeśli pracownik pierwszej linii wybiera zadanie w wydziale produkcyjnym w module Supply Chain Management widzi [odpowiednie przewodniki](#logic) na karcie zadań. Gdy pracownik wybiera określony przewodnik, na ekranie jest wyświetlany kod QR dla tego przewodnika. Następnie pracownik używa okularów HoloLens do skanowania kodu QR, który uruchamia przewodniki i pokazuje wymagane instrukcje.

W poniższych podsekcjach opisano kilka wybranych scenariuszy, w których firmy mogą zobaczyć największą wartość przy użyciu przewodników w celu przedstawienia instrukcji dotyczących produkcji.

### <a name="assembly"></a>Zestaw

![Używanie przewodników w zadaniach montażu.](media/instruction-guides-hero-assembly.png "Używanie przewodników w zadaniach naprawy")

Instrukcje w operacjach montażu pokazują pracownikom potrzebne narzędzia i części oraz sposób ich użycia w rzeczywistej sytuacji.

Menedżerowie produkcji mogą tworzyć i przypisywać przewodniki, na przykład dla [marszrut produkcji](routes-operations.md), [relacji operacji](routes-operations.md#operation-relations)lub [listy BOM](bill-of-material-bom.md). Pracownicy mogą znaleźć odpowiednie instrukcje na temat czynności związanych z produkcją w wydziale produkcyjnym.

### <a name="service"></a>Serwis

![Używanie przewodników w zadaniach naprawy.](media/instruction-guides-hero-service.png "Używanie przewodników w zadaniach naprawy")

Wyposaż techników w szczegółowe instrukcje w miejscu pracy, eliminując konieczność planowania dodatkowych wizyt.

Menedżerowie serwisu mogą przypisywać przewodniki na przykład do konkretnych [produktów](../../commerce/product.md), które opisują procedury oceny jakości.

### <a name="quality"></a>Jakość

![Używanie przewodników w zadaniach kontroli jakości.](media/instruction-guides-hero-quality.png "Używanie przewodników w zadaniach kontroli jakości")

Wdrażaj nowe procesy i zapewniaj zwiększoną spójność zmianie wiedzy pracownika w powtarzalne narzędzie.

Menedżerowie ds. kontroli jakość mogą przypisywać przewodniki na przykład do konkretnych [produktów](../../commerce/product.md), które opisują procedury oceny jakości.

### <a name="certifications"></a>Certyfikacje

![Używanie przewodników w zadaniach związanych z certyfikacją.](media/instruction-guides-hero-certification.png "Używanie przewodników w zadaniach związanych z certyfikacją")

Zapewnij, że każdy pracownik spełnia wysokie standardy, szybko określając kto i gdzie potrzebuje pomocy.

### <a name="safety"></a>Bezpieczeństwo

![Używanie przewodników w instrukcjach bezpieczeństwa pracy.](media/instruction-guides-hero-safety.png "Używanie przewodników w instrukcjach bezpieczeństwa pracy")

Przed rozpoczęciem pracy w danym środowisku udostępnij instrukcje, które posłużą do wykonania niebezpiecznych procedur. Dzięki podejściu opartym na rzeczywistości mieszanej pracownicy mogą wykonać niebezpieczne procedury wirtualnie.

Menedżerowie produkcji mogą zapewnić dedykowane instrukcje obsługi materiałów niebezpiecznych lub delikatnych, przypisując instrukcje do [towarów](../../commerce/product.md), [marszrut](routes-operations.md)i [operacji](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Rozpoczynanie pracy z instrukcjami i przewodnikami

Aby włączyć instrukcje w procesach produkcyjnych, Supply Chain Management zapewnia gotową integrację z systemem Dynamics 365 Guides. Licencjonowana i zainstalowana instancja Guides jest wymagana do tworzenia, obsługiwania i przypisywania instrukcji typu „rzeczywistość mieszana” do środków produkcji i pracy.

### <a name="prerequisites"></a>Wymagania wstępne

Aby można było użyć tej funkcji, system musi zawierać następujące elementy:

- Dynamics 365 Supply Chain Management, wersja 10.0.15 lub nowsza
- [Podwójny zapis](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md) dla aplikacji Supply Chain Management.
- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) w wersji 400.0.1.48 lub nowszej

### <a name="turn-on-the-feature"></a>Włączanie funkcji

Aby funkcja była dostępna w systemie, należy włączyć jej klucze konfiguracji. Wystarczy zrobić to tylko raz. W tym celu administrator musi wykonać następujące czynności:

1. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Rozwiń Sekcję **Rzeczywistość mieszana**, a następnie zaznacz pole wyboru **Przewodnik w rzeczywistości mieszanej**.
1. Rozwiń sekcję **Zarządzanie produkcją**, a następnie zaznacz pole wyboru **Instrukcje produkcji**.
1. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Konfigurowanie sposobu wyświetlania przewodników w wydziale produkcyjnym

Aby skonfigurować sposób wyświetlania przewodników w wydziale produkcyjnym, przejdź do opcji **Rzeczywistość mieszana \> Dynamics 365 Guides \> Konfiguruj integrację przewodników**.

![Konfigurowanie integracji przewodników dla produkcji.](media/instruction-guides-configure-integration.png "Konfigurowanie integracji przewodników dla produkcji")

Ustaw wartości w następujących polach:

- **Adres URL Microsoft Dataverse** — umożliwia określenie adresu URL środowiska Microsoft Dataverse, w którym tworzone są przewodniki. Format to „contoso.crm4.dynamics.com”, gdzie pierwszą część adresu URL zwykle stanowi nazwa organizacji (np. „contoso.”), druga część jest specyficzna dla obszaru danych danego środowiska (np. „crm4.”), a ostatnia część to domena (np. „dynamics.com”). Jednym ze sposobów znalezienia odpowiedniego adresu URL jest przejście do witryny [home.dynamics.com](https://home.dynamics.com/), a następnie otwarcie aplikacji Guides. Po otwarciu przewodników na pasku adresu przeglądarki widoczny będzie adres URL (należy wziąć pod uwagę tylko podstawowy adres URL, który powinien być podobny do powyższego przykładu). Ta wartość jest używana do tworzenia adresów dla przewodników i zostanie zaszyfrowana w kodach QR.
- **Rozmiar kodu QR** — umożliwia ustawienie rozmiaru renderowanego kodu QR. Zalecamy wybór rozmiaru, który wypełni większość ekranu, ale nie cały. Zazwyczaj *15* jest dobrą wartością.
- **Poziom korekcji błędów kodu QR** — umożliwia ustawienie stopnia szczegółowości kodu QR. Wyższa dokładność może zwiększyć niezawodność kodu, ale **rozmiar kodu QR** musi być na tyle duży, aby obsługiwał poziom szczegółowości wymagany na wybranym poziomie korekty.

> [!TIP]
> - Wyświetlenie kodów QR, które są zbyt duże może trwać nieco dłużej. Zostaną przeskalowane w celu dopasowania do ekranu. Nie są one przydatne.
> - Zbyt małe kody QR mogą zmniejszyć zdolność HoloLens do prawidłowego odczytywania kodu w niektórych środowiskach.
> - Zaleca się przetestowanie ustawień dla każdego urządzenia, które będzie wyświetlać kody QR użytkownikom HoloLens. Wybierz ustawienia, które zapewniają wystarczającą czytelność w środowisku wydziału produkcyjnego.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Przegląd wszystkich przypisań przewodnika

Strona **Wszystkie przewodniki** umożliwia wyświetlenie listy wszystkich dostępnych przewodników w organizacji oraz wszystkich przydziałów do procesów produkcyjnych i zasobów. Aby ją otworzyć, należy przejść do **Rzeczywistość mieszana \> Przewodniki \> Wszystkie przewodniki**. Na liście u góry są widoczne wszystkie dostępne przewodniki i można je filtrować, korzystając z pola w tym miejscu. Lista na dole zawiera wszystkie przypisania przewodników oraz pasek narzędzi służący do zarządzania nimi.

![Zarządzanie przewodnikami.](media/instruction-guides-allguides.png "Zarządzanie przewodnikami")

W poniższych sekcjach opisano typy obiektów, do których można przypisać przewodniki. Każdy przypisany przewodnik zawiera instrukcje, które są automatycznie dołączane do odpowiednich zadań produkcyjnych i będą dostępne w wydziale produkcyjnym.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Kojarzenie przewodnika z zasobem

Umożliwia dodanie przewodnika do [zasobu](operations-resources.md) w celu udostępnienia przewodnika w kontekście odpowiednich zadań produkcyjnych.

### <a name="typical-scenario-using-resources"></a>Typowy scenariusz korzystający z zasobów

Można na przykład dołączyć przewodnik z ogólnymi informacjami o bezpieczeństwie maszyny lub instrukcje obsługi do zasobu typu maszyna. Następnie przewodnik będzie dostępny we wszystkich zadaniach wykonywanych na tej maszynie.

### <a name="add-a-guide-to-a-resource"></a>Dodawanie przewodnika do zasobu

Aby dodać przewodnik do zasobu:

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Zasoby \> Zasoby**.
1. Z okienka listy wybierz zasób, do którego chcesz przypisać przewodnik.
1. Rozwiń skróconą kartę **Skojarzone przewodniki**.
1. Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**. Nowy wiersz zostanie dodany do siatki.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany. W przypadku dużej liczby przewodników można filtrować listę, aby znaleźć odpowiedni.
    ![Zarządzanie przewodnikami.](media/instruction-guides-allguides.png "Zarządzanie przewodnikami")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Kojarzenie przewodnika z grupą zasobów

Można dodać Przewodnik do [grup zasobów](tasks/define-discrete-manufacturing-resource-group.md), jeśli są one używane do zarządzania grupami maszyn, linii produkcyjnych lub komórek roboczych.

### <a name="typical-scenarios-using-resource-groups"></a>Typowe scenariusze korzystające z grup zasobów

**Przykład 1:** zdefiniowano grupę zasobów dla tego samego modelu kilku maszyn. Zamiast przypisywać odpowiedni przewodnik obsługi modelu maszyny do każdego odpowiedniego zasobu, można przypisać przewodnik do grupy zasobów odpowiadającej danemu modelowi maszyny.

**Przykład 2:** zdefiniowano grupę zasobów dla komórki roboczej, która zawiera różne maszyny, i istnieje przewodnik zawierający ogólne instrukcje dotyczące obsługi komórki roboczej. Przewodnik ma zastosowanie do każdego działania produkcyjnego w tej komórce roboczej.

### <a name="add-a-guide-to-a-resource-group"></a>Dodawanie przewodnika do grupy zasobów

Aby dodać przewodnik do grupy zasobów:

1. Wybierz kolejno opcje **Kontrola produkcji \> Ustawienia \> Zasoby \> Grupy zasobów**.
1. Z okienka listy wybierz grupę zasobów, do której chcesz przypisać przewodnik.
1. Rozwiń skróconą kartę **Skojarzone przewodniki**.
1. Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**. Nowy wiersz zostanie dodany do siatki.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany. W przypadku dużej liczby przewodników można filtrować listę, aby znaleźć odpowiedni.
    ![Dodawanie przewodnika do grupy zasobów.](media/instruction-guides-resourcegroup.png "Dodawanie przewodnika do grupy zasobów")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Kojarzenie przewodnika ze zwolnionym produktem

Można dodać przewodnik do dowolnego [zwolnionego produktu](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Typowy scenariusz używający zwolnionych produktów

Przewodniki na poziomie produktu wspomagają pracownikom wydziału produkcyjnego instrukcjami dotyczącymi działania lub obsługi określonego zwolnionego produktu lub towaru.

### <a name="add-a-guide-to-a-released-product"></a>Dodawanie przewodnika do zwolnionego produktu

Aby dodać przewodnik do zwolnionego produktu:

1. Przejdź do **Zarządzanie informacjami o produkcji \> Produkty \> Zwolnione produkty**.
1. Otwórz produkt, do którego chcesz przypisać przewodnik.
1. W okienku akcji otwórz kartę **Inżynier** i z grupy **Widok** wybierz pozycję **Skojarzone przewodniki**.
1. Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranego produktu.
1. W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli. 
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do zwolnionego produktu.](media/instruction-guides-ReleasedProduct-AddGuides.png "Dodawanie przewodnika do zwolnionego produktu")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Kojarzenie przewodnika z formułą

Można dodać przewodnik do dowolnej [formuły](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Typowy scenariusz korzystający z formuł
  
Przewodniki na poziomie formuły dostarczają pracownikom wydziału produkcyjnego instrukcje obsługi w kontekście formuły lub receptury. Przewodniki można również przypisywać do wersji formuły.

> [!NOTE]
> Istnieje możliwość przypisania wskazówek dotyczących procesów produkcyjnych na podstawie formuły do marszruty, wersji marszruty lub relacji operacji marszruty.  

> Nie można obecnie dołączać przewodników do pojedynczych wierszy formuły.

### <a name="add-a-guide-to-a-formula"></a>Dodawanie przewodnika do formuły

Aby dodać przewodnik do formuły:

1. Wybierz kolejno opcje **Zarządzanie informacjami o produkcji \> Listy składowe (BOM) i formuły \> Formuły**.
1. Otwórz formułę, do której chcesz przypisać przewodnik.
1. Otwórz kartę **Nagłówek** nad górną skróconą kartą.
1. Rozwiń skróconą kartę **Skojarzone przewodniki**.
1. Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**. Nowy wiersz zostanie dodany do siatki.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do formuły.](media/instruction-guides-Formula.png "Dodawanie przewodnika do formuły")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Kojarzenie przewodnika z wersją formuły

Można dodać przewodnik do dowolnej [wersji formuły](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Typowy scenariusz korzystający z wersji formuły

Przewodniki dołączone do poszczególnych wersji formuły udostępniają pracownikom wydziału produkcyjnego instrukcje dotyczące produkcji tej wersji receptury formuły.

> [!TIP]
> Istnieje możliwość przypisania wskazówek dotyczących procesów produkcyjnych na podstawie tej wersji formuły do marszruty, wersji marszruty lub relacji operacji marszruty.  

> [!NOTE]
> Nie można obecnie dołączać przewodników do pojedynczych wierszy formuły.

### <a name="add-a-guide-to-a-formula-version"></a>Dodawanie przewodnika do wersji formuły

Aby dodać przewodnik do wersji formuły:

1. Wybierz kolejno opcje **Zarządzanie informacjami o produkcji \> Listy składowe (BOM) i formuły \> Formuły**.
1. Otwórz formułę zawierającą wersję, do której chcesz przypisać przewodnik.
1. Otwórz kartę **Nagłówek** nad górną skróconą kartą.
1. Na skróconej karcie **Wersje formuły** wybierz wersję, do której chcesz przypisać przewodnik.
1. Na pasku narzędzi **Wersje formuły** wybierz opcję **Skojarzone przewodniki**.
    ![Otwieranie przewodników skojarzonych z wybraną wersją formuły.](media/instruction-guides-FormulaVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją formuły")
1. Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji formuły.
1. W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli. 
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do wersji formuły.](media/instruction-guides-FormulaVersionAddGuide.png "Dodawanie przewodnika do wersji formuły")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Kojarzenie przewodnika z listą składową (BOM)

Można dodać przewodnik do dowolnej [listy składowej](bill-of-material-bom.md) (BOM).

### <a name="typical-scenario-using-bills-of-materials"></a>Typowy scenariusz korzystający z listy składowej

Przewodniki dołączone do BOM zapewniają pracownikom wydziału produkcji instrukcje opisujące sposób przygotowywania i obsługi materiałów z BOM. Przewodniki można również przypisywać do BOM.

> [!NOTE]
> Nie można obecnie dołączać przewodników do pojedynczych wierszy BOM.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Dodawanie przewodnika do listy składowej (BOM)

Aby dodać przewodnik do listy składowej (BOM):

1. Wybierz kolejno opcje **Zarządzenie informacjami o produkcji \> Lista składowe (BOM) i formuły \> Listy składowe (BOM)**.
1. Otwórz listę składową (BOM), do której chcesz przypisać przewodnik.
1. Otwórz kartę **Nagłówek** nad górną skróconą kartą.
1. Rozwiń skróconą kartę **Skojarzone przewodniki**.
1. Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**. Nowy wiersz zostanie dodany do siatki.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do BOM.](media/instruction-guides-BOM.png "Dodawanie przewodnika do listy składowej (BOM)")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Kojarzenie przewodnika z wersją listy składowej (BOM)

Można dodać przewodnik do dowolnej [wersji listy składowej](bill-of-material-bom.md#bom-and-formula-versions) (BOM).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Typowy scenariusz korzystający z listy składowej (BOM)

Przewodniki dołączone do poszczególnych wersji BOM dostarczają pracownikom warsztatów instrukcje, które opisują sposób przygotowania i obsługi materiałów dla wersji BOM, która różni się od ogólnej listy BOM lub innych jej wersji.

> [!NOTE]
> Nie można obecnie dołączać przewodników do pojedynczych wierszy BOM.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Dodawanie przewodnika do wersji listy składowej (BOM)

Aby dodać przewodnik do wersji listy składowej (BOM):

1. Wybierz kolejno opcje **Zarządzenie informacjami o produkcji \> Lista składowe (BOM) i formuły \> Listy składowe (BOM)**.
1. Otwórz BOM zawierającą wersję, do której chcesz przypisać przewodnik.
1. Otwórz kartę **Nagłówek** nad górną skróconą kartą.
1. Na skróconej karcie **Wersje BOM** wybierz wersję, do której chcesz przypisać przewodnik.
1. Na pasku narzędzi **Wersje BOM** wybierz opcję **Skojarzone przewodniki**.
    ![Otwieranie przewodników skojarzonych z wybraną wersją BOM.](media/instruction-guides-BOMVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją BOM")
1. Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji BOM.
1. W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do wersji BOM.](media/instruction-guides-BOMVersionAddGuide.png "Dodawanie przewodnika do wersji BOM")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Kojarzenie przewodnika z marszrutą

Można dodać przewodnik do dowolnej [marszruty](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Typowy scenariusz korzystający z marszrut

Marszruty służą zwykle do określania sposobu, w jaki dany zwolniony produkt jest produkowany na podstawie BOM lub wersji BOM oraz za pomocą zestawu zasobów lub grup zasobów.

Przypisz przewodnik do marszruty, aby zapewnić instrukcje krok po kroku dotyczące odpowiedniego procesu produkcji.

### <a name="add-a-guide-to-a-route"></a>Dodawanie przewodnika do marszruty

Aby dodać przewodnik do marszruty:

1. Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.
1. Otwórz marszrutę, do której chcesz przypisać przewodnik.
1. Rozwiń skróconą kartę **Skojarzone przewodniki**.
1. Wybierz opcję **Dodaj** na pasku narzędzi **Skojarzone przewodniki**. Nowy wiersz zostanie dodany do siatki.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do marszruty.](media/instruction-guides-Route.png "Dodawanie przewodnika do marszruty")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Kojarzenie przewodnika z wersją marszruty

Można dodać przewodnik do dowolnej [wersji marszruty](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Typowy scenariusz korzystający z wersji marszruty

Wersje marszrut są zwykle używane do określania wariantów procesów produkcyjnych na podstawie istniejącej marszruty. Do każdej wersji marszruty można przypisać różne przewodniki.

### <a name="add-a-guide-to-a-route-version"></a>Dodawanie przewodnika do wersji marszruty

Aby dodać przewodnik do wersji marszruty:

1. Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.
1. Otwórz marszrutę, do której chcesz przypisać przewodnik.
1. Na skróconej karcie **Wersje** wybierz wersję, do której chcesz przypisać przewodnik.
1. Na pasku narzędzi **Wersje** wybierz opcję **Skojarzone przewodniki**.
    ![Otwieranie przewodników skojarzonych z wybraną wersją marszruty.](media/instruction-guides-RouteVersion.png "Otwieranie przewodników skojarzonych z wybraną wersją marszruty")
1. Zostanie wyświetlona strona **Skojarzone przewodniki** dla wybranej wersji BOM.
1. W okienku akcji wybierz opcję **Dodaj**, aby dodać nowy wiersz do tabeli.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany.
    ![Dodawanie przewodnika do wersji marszruty.](media/instruction-guides-RouteVersionAddGuide.png "Dodawanie przewodnika do wersji marszruty")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Kojarzenie przewodnika z relacją operacji marszruty

Można dodać przewodnik do dowolnej [relacji operacji marszruty](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Typowy scenariusz używający relacji operacji marszruty

Relacje operacji są najbardziej szczegółowym sposobem dodawania wskazówek do procesu produktu oraz związanych z nim operacji. Można określić wytyczne dla każdej operacji w marszrucie i określić różne wskazówki dla każdego typu kontekstu relacji określonego dla marszruty, na przykład dla określonych towarów, konfiguracji itp. Można również określić etapy operacji, na które mają być stosowane wskazówki (np. ustawienia, kolejkowanie, proces lub transport).

> [!NOTE]
> Jeśli dla kilku relacji operacji w marszrucie zostaną określone przewodniki, w oddziale produkcyjnym dla wygenerowanych zadań będą wyświetlane tylko informacje o przewodniku z najbardziej szczegółowej relacji.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Dodawanie przewodnika do relacji operacji marszruty

Aby dodać przewodnik do relacji operacji marszruty:

1. Przejdź do **Kontrola produkcji \> Wszystkie marszruty**.
1. Otwórz marszrutę, do której chcesz przypisać przewodnik.
1. W okienku akcji otwórz kartę **Marszruta** i z grupy **Obsługa** wybierz pozycję **Szczegóły marszruty**.
1. Zostanie otwarta strona **Szczegóły marszruty** dla wybranej marszruty.
1. W górnej tabeli wybierz operację, dla której chcesz podać wskazówki.
1. W dolnej tabeli wybierz określoną relację (lub ogólną relację **Wszystkie**).
    ![Wybór operacji, a następnie jej relacji.](media/instruction-guides-RouteOperationRelation.png "Wybór operacji, a następnie jej relacji")
1. Nad dolną tabelą otwórz kartę **Skojarzone przewodniki**. ![Karta Skojarzone przewodniki.](media/instruction-guides-RouteOperationRelation-AddGuide.png "Karta Skojarzone przewodniki")
1. Wybierz opcję **Dodaj** z paska narzędzi u góry dolnej tabeli, aby dodać nowy wiersz do tabeli.
1. W przypadku nowego wiersza należy użyć listy rozwijanej w kolumnie **Nazwa**, aby wybrać przewodnik, który ma zostać przypisany. W pozostałej części wiersza zaznacz pole wyboru dla każdego kontekstu, w którym ma być dostępny wybrany przewodnik.

> [!NOTE]
> Można dodać jedną lub więcej przewodników dla każdego etapu operacji.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Wybór przewodnika z interfejsu obsługi wydziału produkcyjnego

Gdy pracownik otwiera listę zadań w interfejsie obsługi wydziału produkcyjnego, moduł Supply Chain Management znajduje odpowiednie przewodniki dla pokazanych zadań. Użyj przycisku **Przewodniki**, aby wyświetlić odpowiednie przewodniki.

![Przycisk Przewodniki w interfejsie obsługi wydziału produkcyjnego.](media/instruction-guides-Shopfloor1.png "Przycisk Przewodniki w interfejsie obsługi wydziału produkcyjnego")

Następnie załóż odpowiednie HoloLens i uzyskaj dostęp do odpowiedniego przewodnika, patrząc na kod QR i włączając odpowiedni przewodnik.

![Kod QR dostępu do przewodników przy użyciu HoloLens.](media/instruction-guides-Shopfloor2.png "Kod QR dostępu do przewodników przy użyciu HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Rozpoznawanie logiki wybierania przewodników

Można dodać przewodniki do następujących danych produkcyjnych:

- [Zasoby](#resources)
- [Grupy zasobów](#resource-groups)
- [Zwolnione produkty](#released-products)
- [Formuły](#formulas)
- [Wersje formuły](#formula-versions)
- [List składowych (BOM)](#bom)
- [Wersji BOM](#bom-versions)
- [Marszruty](#routes)
- [Wersje marszruty](#route-versions)
- [Relacji operacji marszrut](#route-operation-relations)

Jeśli moduł Supply Chain Management generuje zadania dla wydziału produkcyjnego, system pobierze odpowiednie przewodniki z tych źródeł. Zwróć uwagę na następujące ważne reguły.

- W przypadku dołączania wersji BOM lub wersji formuły do marszruty lub zlecenia produkcyjnego wszystkie przewodniki dołączone do tej wersji, a także do nadrzędnego BOM lub formuły w tej wersji zostaną wyświetlone w zadaniu.
- W przypadku dołączania wersji marszruty do zlecenia produkcyjnego wszystkie przewodniki dołączone do tej wersji, a także do nadrzędnej marszruty w tej wersji zostaną wyświetlone w zadaniu.
- W przypadku zdefiniowania kilku relacji operacji marszruty, które obejmują relację *Wszystkie* i przypisywania do nich przewodników w danym zadaniu będą wyświetlana tylko przewodniki z najbardziej szczegółowej relacji.  

![Diagram rozpoznawania odpowiednich przewodników.](media/instruction-guides-Resolve.png "Diagram rozpoznawania odpowiednich przewodników")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]