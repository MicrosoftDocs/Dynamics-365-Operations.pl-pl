---
title: Projektowanie nowego rozwiązania raportowania elektronicznego do drukowania etykiet ZPL
description: W tym artykule wyjaśniono, jak zaprojektować nowe rozwiązanie do raportowania elektronicznego (ER) do drukowania etykiet w języku programowania Zebra (ZPL).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f861fe63c6d7d00d0a9f84d33c0d1b1b23735b61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845723"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>Projektowanie nowego rozwiązania raportowania elektronicznego do drukowania etykiet ZPL

[!include [banner](../includes/banner.md)]


W tym artykule wyjaśniono, w jaki sposób użytkownik w roli Administrator systemu, Deweloper raportowania elektronicznego lub Konsultant funkcjonalny raportowania elektronicznego może konfigurować parametry struktury [Raportowanie elektroniczne (ER)](general-electronic-reporting.md), projektować wymagany raport ER [konfiguracje nowego rozwiązania raportowania elektronicznego](general-electronic-reporting.md#Configuration) w celu uzyskania dostępu do danych system zarządzania magazynem oraz generowanie niestandardowych etykiet lokalizacji magazynów w formacie Zebra Programming Language (ZPL) II. Kroki można wykonać na danych firmy **USRT**.

## <a name="business-scenario"></a>Scenariusz biznesowy

Reprezentujesz firmę, która zaimplementowała zarządzanie magazynem w Microsoft Dynamics 365 Finance. Każda lokalizacja w magazynie musi być oznaczona etykietą samoobsługową, która zawiera kod pocztowy. Pracownicy magazynu będą używać ręcznych czytników kodów kreskowych do skanowania kodów kreskowych.

Wszystkie lokalizacje magazynowe zostały oznakowane w zakresie działań pre-go-live. Należy jednak mieć również możliwość drukowania etykiet lokalizacji magazynowych na żądanie, jeśli istniejące etykiety ulegną uszkodzeniu lub gdy regały magazynowe zostaną przekonfigurowane. Korzystając z niedawno wydanej funkcji ER, można skonfigurować nowe rozwiązanie ER, które umożliwia kierownikowi magazynu drukowanie etykiet bezpośrednio na termicznej drukarce etykiet.

## <a name="configure-the-er-framework"></a>Konfigurowanie struktury ER

Wykonaj kroki opisane w sekcji [Konfigurowanie platformy ER](er-quick-start2-customize-report.md#ConfigureFramework), aby skonfigurować minimalny zestaw parametrów ER. Tę konfigurację należy ukończyć przed rozpoczęciem korzystania z platformy ER do projektowania nowego rozwiązania ER.

## <a name="design-a-domain-specific-data-model"></a>Projektowanie modelu danych specyficznego dla domeny

Należy utworzyć nową konfigurację ER, która zawiera składnik [modelu danych](er-overview-components.md#data-model-component) dla domeny biznesowej Warehouse management. Ten model danych będzie później używany jako źródło danych podczas projektowania formatu raportowania elektronicznego w celu generowania etykiet lokalizacji magazynu.

### <a name="import-a-data-model-configuration"></a>Importowanie konfiguracji modelu danych

Aby zaimportować wymagany model danych z pliku XML dostarczonego przez firmę Microsoft, należy wykonać następujące kroki. Można również utworzyć własny model danych w sposób opisany w następnej sekcji.

1. Pobierz [Warehouse model.wersja.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **model magazynu.wersja.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

![Zaimportowana konfiguracja modelu danych ER na stronie Konfiguracje.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>Stwórz model danych konfiguracji

Zamiast importować plik modelu danych dostarczony przez firmę Microsoft, można utworzyć model danych od początku. Aby uzyskać przykład, który pokazuje, jak wykonać to zadanie, zobacz temat [Tworzenie nowej konfiguracji modelu danych](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>Przejrzyj model danych

Można wyświetlić edytowalna wersję skonfigurowanego modelu danych na stronie **konstruktora modelu danych**.

![Struktura modelu danych ER na stronie projektanta modeli danych.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>Umożliwia zaprojektowanie mapowania modelu dla skonfigurowanego modelu danych

Jako użytkownik w roli Deweloper raportowania elektronicznego musisz utworzyć nową konfigurację ER zawierającą zawiera składnik mapowania modelu dla modelu danych [magazynu](er-overview-components.md#model-mapping-component). Ten składnik implementuje skonfigurowany model danych dla Dynamics 365 Finance i jest specyficzny dla tej aplikacji. Należy go skonfigurować, aby określić obiekty aplikacji, które będą używane do wypełniania skonfigurowanego modelu danych danymi aplikacji w czasie wykonywania. Aby wykonać to zadanie, musisz zrozumieć, w jaki sposób struktura danych domeny biznesowej Warehouse management jest implementowana w finansach.

### <a name="import-a-model-mapping-configuration"></a>Importowanie konfiguracji mapowania modelu

Wykonaj poniższe czynności, aby zaimportować wymagane mapowanie modelu z pliku XML dostarczonego przez firmę Microsoft. Alternatywnie możesz utworzyć własne mapowanie modelu, jak opisano w następnej sekcji.

1. Pobierz [Mapowanie magazynów.wersja.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Mapowanie magazynów.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

![Zaimportowana konfiguracja mapowania modelu ER na stronie Konfiguracje.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>Stwórz model konfiguracji mapowania

Zamiast importować plik mapowania modelu dostarczony przez firmę Microsoft, można utworzyć mapowanie modelu od podstaw. Aby uzyskać przykład, który pokazuje, jak wykonać to zadanie, zobacz temat [Utwórz nową konfigurację mapowania modelu](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>Przeglądanie mapowania modelu

Możesz wyświetlić edytowalną wersję skonfigurowanego mapowania modelu na stronie **Projektant mapowania modeli**.

![Struktura mapowania modelu ER na stronie Projektant mapowania modelu.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>Projektowanie formatu

Jako użytkownik pełniący rolę konsultanta funkcjonalnego raportowania elektronicznego należy utworzyć nową konfigurację ER zawierającą komponent [formatu](er-overview-components.md#format-component). Aby skonfigurować ten składnik, użyj kodu ZPL II do określenia układu etykiety lokalizacji w magazynie.

### <a name="import-a-format-configuration"></a>Import konfiguracji formatu

Wykonaj poniższe czynności, aby zaimportować wymagany format z pliku XML dostarczonego przez firmę Microsoft. Alternatywnie możesz utworzyć własny format, jak opisano w następnej sekcji.

1. Pobierz [Etykiety lokalizacji magazynów.wersja.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) i zapisz go na komputerze lokalnym.
2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. W obszarze roboczym **raportowanie elektroniczne** wybierz **konfiguracje raportowania**.
4. Na stronie **Konfiguracje**, w okienku akcji wybierz **Eksport** \> **Załaduj z pliku XML**.
5. Wybierz opcję **Przeglądaj**, a następnie znajdź i wybierz **Etykiety lokalizacji magazynów.wersja.1.1.xml**.
6. Wybierz przycisk **OK**, aby importować konfigurację.

![Zaimportowana konfiguracja formatu ER na stronie Konfiguracje.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>Tworzenie konfiguracji formatu

Zamiast importować plik formatu dostarczonego przez firmę Microsoft, możesz utworzyć format od podstaw. Aby uzyskać przykład, który pokazuje, jak wykonać to zadanie, zobacz temat [Utwórz nową konfigurację formatu](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>Przeglądanie formatu

Możesz wyświetlić edytowalną wersję skonfigurowanego formatu na stronie **Projektant formatów**.

![Struktura formatu ER na stronie Projektant formatów.](./media/er-design-zpl-labels-format.png)

Źródło `model.Location.Label` danych tego formatu jest skonfigurowane do generowania etykiet zawierających następujące informacje:

- Tytuł magazynu jako tekst
- Tytuł magazynu jako kod pocztowy
- Tytuł lokalizacji
- Cyfry kontrolne

Na stronie **konstruktora formuły** dotyczącej źródła danych formuła ER używana do generowania etykiet zawiera funkcję `CONCATENATE` łączącą informacje w żądanym układzie.

![Formuła źródła danych na stronie Projektant formuł.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> Układ etykiety jest tak zaprojektowany, aby tytuł lokalizacji i cyfry kontrolne były wyrównane do środka etykiety. Jednak kod ZPL II nie obsługuje wyrównania centrów dla kodów kreskowych. W związku z tym formuła `model.Location.Warehouse.Alignment` źródła danych służy do wyrównania kodu tekstowego w środku etykiety. Ta formuła oblicza lewe przesunięcie kodu kreskowego na podstawie liczby znaków w tytule magazynu.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>Przygotuj środowisko do wyświetlania podglądu wygenerowanych etykiet

Poniższy przykład wykorzystuje aplikację emulatora drukarki do etykiet ZPL, aby wyświetlić podgląd wygenerowanych etykiet na ekranie. Wykonaj poniższe czynności, aby włączyć tę opcję.

1. Dodaj [Miejsce docelowe drukarki](er-destination-type-print.md) ER dla formatu **Etykieta lokalizacji magazynu** ER i skonfiguruj go do wysyłania wygenerowanych etykiet z finansów do [Document routing agent (DRA)](install-document-routing-agent.md).
2. Należy zainstalować i skonfigurować DRA do oznaczania marszruty wygenerowanych przez finanse na lokalnej drukarce, która jest dostępna z bieżącej stacji roboczej.
3. Dodaj drukarkę lokalną dla bieżącej stacji roboczej i skonfiguruj ją tak, aby przekazywała wygenerowane etykiety z agenta DRA do aplikacji emulatora drukarki.
4. Zainstaluj aplikację emulatora drukarki jako rozszerzenie przeglądarki internetowej Chrome i skonfiguruj ją tak, aby przekazywał wygenerowane etykiety z drukarki lokalnej do usługi sieciowej, która będzie renderować wygenerowane etykiety i zwracać je do emulatora drukarki w celu podglądu.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>Raport ER</p>
<p>Miejsce docelowe — drukarka</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>Agent rozsyłania dokumentów</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>Drukarka lokalna</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>Emulator drukarki</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>Renderowanie usługi internetowej</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>Instalowanie i konfigurowanie aplikacji emulatora drukarek

Dodaj aplikację emulatora drukarek do aparatu renderowania ZPL do przeglądarki internetowej Chrome. W tym przykładzie jest [używany emulator drukarki ZPL](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) oparty na usłudze [sieci web Labelary ZPL](http://labelary.com/service.html). Aplikacja emulatora drukarki przekaże wygenerowane etykiety w formacie ZPL z drukarki lokalnej do usługi internetowej, a następnie zwróci etykiety jako pliki PDF lub PNG do podglądu.

1. W chromowanych sklepach sieci web znajdź i wybierz aplikację emulatora drukarki, której chcesz używać. Następnie wybierz opcję **Dodaj do Chrome** przeglądarki, aby dodać ją do przeglądarki internetowej Chrome.

    ![Dodanie aplikacji emulatora drukarki do przeglądarki internetowej Chrome ze sklepu internetowego Chrome.](./media/er-design-zpl-labels-add-app.png)

2. Wybierz **Uruchom aplikację**, aby uruchomić aplikację emulatora drukarki z przeglądarki internetowej Chrome.

    ![Uruchamianie aplikacji emulatora drukarki z przeglądarki internetowej Chrome.](./media/er-design-zpl-labels-run-app.png)

3. Skonfiguruj uruchomioną aplikację:

    1. Wyłącz aplikację.
    2. W ustawieniach drukarki ustaw hosta na **127.0.0.1**.
    3. Ustaw port na **9100**.

        ![Konfigurowanie aplikacji emulatora drukarki.](./media/er-design-zpl-labels-configure-app.png)

    4. Wyłącz z powrotem aplikację. Powinien pojawić się komunikat informujący, że drukarka została uruchomiona na określonym hoście i porcie.

        ![Aplikacja emulatora drukarki jest włączona ponownie.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> Ponieważ aplikacja emulatora drukarki używana w tym przykładzie opiera się na usłudze sieci Web do renderowania etykiet, upewnij się, że ustawienia zabezpieczeń umożliwiają komunikację z usługą. W przeciwnym razie aplikacja nie otrzyma wyrenderowanych etykiet, a podgląd tych etykiet nie będzie dostępny.

### <a name="add-and-configure-a-local-printer"></a>Dodawanie i konfigurowanie lokalnej drukarki

[Dodaj nową drukarkę lokalną](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b), której bieżące urządzenie może używać do przekazywania wygenerowanych etykiet z agenta DRA do aplikacji emulatora drukarki.

1. W systemie Windows wybierz **Start** \> **Ustawienia** \> **Urządzenia** \> **Drukarki \& skanery**.
2. Wybierz **Ustawienia skanerów \& drukarek**.
3. Aby **dodać drukarkę lub skaner**, wybierz pozycję **Dodaj urządzenie**.
4. W **przypadku drukarki, której nie ma na liście**, wybierz opcję **Dodaj ręcznie**.
5. W polu **Znajdź drukarkę według innych** opcji wybierz **opcję Dodaj drukarkę lokalną lub drukarkę sieciową z ustawieniami ręcznymi**.
6. W polu **Wybierz port drukarki** wybierz pozycję **Utwórz nowy port**, a następnie wykonaj następujące czynności:

    1. W polu **Typ portu** wybierz opcję **Standardowy port TCP/IP**.
    2. W polu **Nazwa hosta lub adres** IP wprowadź **127.0.0.1**.
    3. Wprowadź **Nazwa portu** w polu, wpisz **ZPL**.
    4. Poczekaj, aż operacja **Wykrywanie portu TCP/IP** zostanie zakończona.
    5. W polu **Typ urządzenia** wybierz **Niestandardowe**, a następnie **Ustawienia**.
    6. Upewnij się, że zostały określone następujące ustawienia portu:

        - **Nazwa portu:** ZPL
        - **Nazwa drukarki lub adres IP:** 127.0.0.1
        - **Protokół:** nieprzetworzone
        - **Numer portu:** 9100

7. W polu **Zainstaluj sterownik drukarki** wybierz opcję **Ogólne/Tylko tekst**.
8. W polu **Nazwa drukarki** wprowadź **ZebraPrinter**.

![Dodawanie lokalnej drukarki dla bieżącego urządzenia.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>Zainstaluj i skonfiguruj agenta DRA

Przygotuj DRA do przekazania wygenerowanych etykiet z finansów do skonfigurowanej drukarki lokalnej.

1. [Instalowanie DRA](install-document-routing-agent.md#install-the-document-routing-agent).
2. [Konfigurowanie DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [Zarejestruj drukarkę lokalną](install-document-routing-agent.md#register-network-printers) w DRA.
4. [Uaktywnij drukarkę lokalną](install-document-routing-agent.md#administer-network-printers) w środowisku finansów.

![Przygotowanie agenta DRA do drukowania wygenerowanych etykiet.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>Konfigurowanie miejsca docelowego raportowania elektronicznego

Przygotuj miejsce docelowe ER, aby przekazywać wygenerowane etykiety z finansów do agenta DRA.

1. Wybierz kolejno opcje **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Aplikacja docelowa raportowania elektronicznego**.
2. Na stronie **Miejsce docelowe raportowania elektronicznego** w okienku akcji naciśnij przycisk **Nowe**.
3. W polu **Odwołanie** wybierz etykiety **lokalizacji magazynu**.
4. Na **skróconej karcie Plik docelowy** wybierz pozycję **Nowy**.
5. W polu **Nazwa** wprowadź nazwę **Etykiety**.
6. W polu **nazwa składnika pliku** wprowadź lub wybierz opcję **Raport**.
7. Wybierz **Ustawienia**.
8. W wyświetlonym oknie dialogowym **Ustawienia lokalizacji docelowej** na karcie **Drukarka** w opcji **Włączone** zaznacz wartość **Tak**.
9. W polu **Nazwa drukarki** wybierz **ZebraPrinter**.
10. W polu **Typ wyboru trasy dokumentu** zaznacz opcję **ZPL**.
11. Kliknij przycisk **OK**.

![Konfigurowanie miejsca docelowego ER dla formatu etykiet lokalizacji magazynu na stronie Docelowe miejsce raportowania elektronicznego.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>Sprawdź lokalizacje magazynów

1. Wybierz kolejno opcje **Warehouse management** \> **Ustawienia** \> **Magazyn** \> **Lokalizacje**.
2. Na stronie **Lokalizacje** filtruj, aby wyświetlić tylko lokalizacje, które mają wartość w **polu Cyfry kontrolne**.

![Przeglądanie lokalizacji magazynów na stronie Lokalizacje.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>Drukuj etykiety lokalizacji w magazynie

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń węzeł **Model magazynu**, a następnie wybierz opcję **Etykiety lokalizacji magazynu**.
3. W okienku akcji wybierz opcję **Uruchom**.
4. W oknie dialogowym **Parametry raportu elektronicznego** na karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.
5. Na karcie **Zakres** znajdź wiersz, w którym pole **Tabela** ma wartość **Lokalizacje**, a pole **Pole** jest ustawione na **Lokalizacja**. W polu **Kryteria** wprowadź wartość **LPEnabled**.
6. Kliknij przycisk **OK**.
7. Kliknij przycisk **OK**. Etykieta jest generowana i pokazywana na stronie podglądu w aplikacji emulatora drukarki.

![Przeglądanie wygenerowanej etykiety na stronie podglądu aplikacji emulatora drukarki Zpl.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>Modyfikowanie układu etykiety

Bieżący układ etykiet lokalizacji w magazynie można zmienić. Poniższy przykład pokazuje, jak zmienić układ, tak aby wygenerowane etykiety zawierały identyfikator profilu lokalizacji.

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Ustawienie opcji **Używaj miejsc docelowych** w [parametrach użytkownika ER](electronic-reporting-destinations.md#applicability) spowoduje, że wartość zmieni się na **Tak**.
3. Na stronie **Konfiguracje** w drzewie konfiguracji rozwiń węzeł **Model magazynu**, a następnie wybierz opcję **Etykiety lokalizacji magazynu**.
4. Wybierz opcję **Konstruktor**.
5. Na stronie **Projektant formatów** na karcie **mapowanie** rozwiń gałąź źródło danych `model.Location.Label`.
6. W oknie dialogowym **Właściwości źródła danych** wybierz pozycję **Edytuj** \> **Edytuj formułę.**
7. Na stronie **Projektant formuły** w polu **Formuła** sprawdź formułę ER używaną do generowania etykiet.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. Zaktualizuj formułę, aby dodać identyfikator profilu lokalizacji do wygenerowanych etykiet.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. Wybierz opcję **Zapisz**.
10. Kliknij przycisk **OK**.
11. W okienku akcji wybierz opcję **Uruchom**.
12. W oknie dialogowym **Parametry raportu elektronicznego** na karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**.
13. Na karcie **Zakres** znajdź wiersz, w którym pole **Tabela** ma wartość **Lokalizacje**, a pole **Pole** jest ustawione na **Lokalizacja**. W polu **Kryteria** wpisz **Bay**.
14. Kliknij przycisk **OK**.
15. Kliknij przycisk **OK**. Etykieta jest generowana i pokazywana na stronie podglądu w aplikacji emulatora drukarki.

![Przejrzyj wygenerowaną etykietę, która zawiera identyfikator profilu lokalizacji na stronie podglądu aplikacji emulatora drukarki Zpl.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>Kodowanie

> [!NOTE]
> Należy zsynchronizować ustawienie kodowania składnika **Wspólny\\Plik** edytowalnego formatu ER i odpowiednie ustawienie zaprojektowanej etykiety. Wartość pola **[Encoding](er-suppress-bom-characters.md)** składnika **Wspólne\\Plik** nie powinna być sprzeczna z poleceniem ZPL używanym do kontrolowania kodowania etykiety (na przykład poleceniem `^CI`). Program ER nie sprawdza, czy te ustawienia są zsynchronizowane.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Miejsce docelowe — drukarka](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
