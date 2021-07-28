---
title: Dodawanie analizy do obszarów roboczych za pomocą Power BI Embedded
description: W tym temacie przedstawiono sposób osadzenia raportu programu Power BI na karcie Analizy w obszarze roboczym.
author: RichdiMSFT
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 14c8c36b90caa3a9378a739932d734b94985b46c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354452"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>Dodawanie analizy do obszarów roboczych za pomocą Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Ta funkcja jest obsługiwana w Finance and Operations (wersja 7.2 i nowsze).

## <a name="introduction"></a>Wprowadzenie
W tym temacie przedstawiono sposób osadzenia raportu programu Microsoft Power BI na karcie **Analizy** w obszarze roboczym. W przedstawionym tutaj przykładzie rozszerzymy obszar roboczy **Zarządzanie rezerwacjami** w aplikacji Zarządzanie flotą w celu osadzenia analitycznego obszaru roboczego na karcie **Analizy**.

## <a name="prerequisites"></a>Wymagania wstępne
+ Dostęp do środowiska deweloperskiego, w którym działa aktualizacja platformy 8 lub nowsza.
+ Raport analityczny (plik .pbix), który został utworzony przy użyciu aplikacji Microsoft Power BI Desktop i ma model danych pochodzący z bazy danych magazynu jednostek.

## <a name="overview"></a>Przegląd
Niezależnie od tego, czy rozszerzasz istniejący obszar roboczy aplikacji, czy wprowadzasz nowy własny obszar roboczy, możesz za pomocą osadzonych widoków analitycznych przekazywać wnikliwy i interaktywny obraz danych biznesowych. Proces dodawania karty analitycznego obszaru roboczego składa się z czterech etapów.

1. Dodanie pliku .pbix jako zasobu usługi Dynamics 365.
2. Zdefiniowanie karty analitycznego obszaru roboczego.
3. Osadzenie zasobu .pbix na karcie obszaru roboczego.
4. Opcjonalnie: Dodanie rozszerzeń w celu dostosowania widoku.

> [!NOTE]
> Aby uzyskać więcej informacji na temat tworzenia raportów analitycznych, zobacz [Wprowadzenie do programu Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/). Ta strona jest świetnym źródłem informacji, które mogą pomóc tworzyć zaawansowane rozwiązania do sprawozdawczości analitycznej.

## <a name="add-a-pbix-file-as-a-resource"></a>Dodanie pliku .pbix jako zasobu
Przed rozpoczęciem należy utworzyć lub pozyskać raport programu Power BI, który zostanie osadzony w obszarze roboczym. Aby uzyskać więcej informacji na temat tworzenia raportów analitycznych, zobacz [Wprowadzenie do programu Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/).

Wykonaj poniższe kroki, aby dodać plik .pbix jako artefakt projektu programu Visual Studio.

1. Utwórz nowy projekt w odpowiednim modelu.
2. W Eksploratorze rozwiązań zaznacz projekt, kliknij go prawym przyciskiem myszy, a następnie wybierz kolejno polecenia **Dodaj** \> **Nowy element**.
3. W oknie dialogowym **Dodaj nowy element** w obszarze **Artefakty operacji** zaznacz szablon **Zasób**.
4. Wprowadź nazwę, która będzie służyć to odwoływania się do raportu w metadanych języka X++, a następnie kliknij przycisk **Dodaj**.

    ![Okno dialogowe Dodaj nowy element.](media/analytical-workspace-add.png)

5. Znajdź plik .pbix zawierający definicję raportu analitycznego, a następnie kliknij przycisk **Otwórz**.

    ![Okno dialogowe Wybierz plik zasobów.](media/analytical-workspace-select-resource.png)

Teraz gdy masz dodany plik .pbix jako zasób usługi Dynamics 365, można osadzać raporty w obszarach roboczych i dodawać bezpośrednie łącza do nich przy użyciu elementów menu.

## <a name="add-a-tab-control-to-an-application-workspace"></a>Dodawanie formantu karty do obszaru roboczego aplikacji
W tym przykładzie rozszerzymy obszar roboczy **Zarządzanie rezerwacjami** w modelu Zarządzanie flotą poprzez dodanie karty **Analizy** do definicji formularza **FMClerkWorkspace**.

Na poniższej ilustracji widać, jak formularz **FMClerkWorkspace** wygląda w projektancie w programie Microsoft Visual Studio.

![Formularz FMClerkWorkspace przed zmianami.](media/analytical-workspace-definition-before.png)

Wykonaj następujące kroki w celu rozszerzenia definicji formularza dla obszaru roboczego **Zarządzanie rezerwacjami**.

1. Otwórz projektanta formularzy w celu rozszerzenia definicji projektu.
2. W definicji projektu zaznacz górny element o nazwie **Projekt | Wzorzec: Działający obszar roboczy**.
3. Kliknij prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Nowy** \> **Karta**, aby dodać nowy formant o nazwie **FormTabControl1**.
4. W projektancie formularza wybierz opcję **FormTabControl1**.
5. Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Strona nowej karty**, aby dodać nową kartę.
6. Zmień nazwę karty na bardziej sugestywną, taką jak **Obszar roboczy**.
7. W projektancie formularza wybierz opcję **FormTabControl1**.
8. Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Strona nowej karty**.
9. Zmień nazwę karty na bardziej sugestywną, taką jak **Analizy**.
10. W projektancie formularza wybierz opcję **Analizy (karta)**.
11. Dla właściwości **Podpis** określ wartość **Analizy**, a w ustawieniu właściwości **Automatyczna deklaracja** określ wartość **Tak**.
12. Kliknij formant prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Nowy** \> **Grupa**, aby dodać nowy formant grupy formularzy.
13. Zmień nazwę grupy formularzy na bardziej sugestywną, taką jak **powerBIReportGroup**.
14. W projektancie formularza wybierz opcję **PanoramaBody (karta)**, a następnie przeciągnij formant na kartę **Obszar roboczy**.
15. W definicji projektu zaznacz górny element o nazwie **Projekt | Wzorzec: Działający obszar roboczy**.
16. Kliknij prawym przyciskiem myszy, a następnie wybierz opcję **Usuń wzorzec**.
17. Ponownie kliknij prawym przyciskiem myszy, a następnie wybierz kolejno opcje **Dodaj wzorzec** \> **Obszar roboczy na kartach**.
18. Wykonaj kompilację, aby sprawdzić działanie wprowadzonych zmian.

Na poniższej ilustracji widać, jak projekt wygląda po zastosowaniu tych zmian.

![Formularz FMClerkWorkspace po zmianach.](media/analytical-workspace-definition-after.png)

Teraz gdy masz dodane formanty formularza, które będą używany do osadzania raportu w obszarze roboczym, należy zdefiniować rozmiar formantu nadrzędnego, aby zmieścił układ. Domyślnie w raporcie będą widoczne strony **Okienko filtrów** i **Karta**. Można jednak zmienić widoczność tych formantów zgodnie z potrzebami docelowego odbiorcy raportu.

> [!NOTE]
> W przypadku osadzonych obszarów roboczych zalecamy, aby dla zachowania spójności za pomocą rozszerzeń ukryć strony **Okienko filtrów** i **Karta**.

Zadanie rozszerzania definicji formularza raportu zostało zakończone. Aby uzyskać więcej informacji o używaniu rozszerzeń do wprowadzania dostosowań, zobacz [Dostosowywanie za pomocą rozszerzeń i nakładania warstw](../extensibility/customization-overlayering-extensions.md).

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>Dodawanie logiki biznesowej języka X++ w celu osadzenia formantu podglądu
Wykonaj następujące kroki, aby dodać logikę biznesową, która inicjuje formant podglądu raportów znajdujący się w obszarze roboczym **Zarządzanie rezerwacjami**.

1. Otwórz projektanta formularza **FMClerkWorkspace** w celu rozszerzenia definicji projektu.
2. Naciśnij klawisz F7, aby uzyskać dostęp do kodu źródłowego kryjącego się za definicją kodu.
3. Dodaj następujący kod źródłowy języka X++.

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. Wykonaj kompilację, aby sprawdzić działanie wprowadzonych zmian.

Zadanie dodawania logiki biznesowej inicjującej formant podglądu osadzonego raportu zostało zakończone. Na poniższej ilustracji widać, jak obszar roboczy wygląda po zastosowaniu tych zmian.

![Raport osadzony w obszarze roboczym.](media/analytical-workspace-final.png)

> [!NOTE]
> Korzystając z kart obszaru roboczego pod tytułem strony, można przejść do istniejącego widoku operacyjnego.

## <a name="reference"></a>Odwołanie

### <a name="pbireporthelperinitializereportcontrol-method"></a>Metoda PBIReportHelper.initializeReportControl
Ten rozdział zawiera informacje o klasie pomocy służącej do osadzania raportu programu Power BI (zasobu .pbix) w formancie grupy formularzy.

#### <a name="syntax"></a>Składnia
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>Parametry

| Nazwisko             | opis                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| resourceName     | Nazwa zasobu .pbix.                                                                              |
| formGroupControl | Formant grupy formularzy, do którego ma zostać zastosowany formant raportu narzędzia Power BI.                                              |
| defaultPageName  | Domyślna nazwa strony.                                                                                       |
| showFilterPane   | Wartość logiczna wskazująca, czy okienko filtrów powinno być wyświetlane (**true**), czy ukryte (**false**).     |
| showNavPane      | Wartość logiczna wskazująca, czy okienko nawigacji powinno być wyświetlane (**true**), czy ukryte (**false**). |
| defaultFilters   | Domyślne filtry raportu programu Power BI.                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]