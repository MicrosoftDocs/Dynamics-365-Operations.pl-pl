---
title: Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne
description: W tym artykule wyjaśniono, jak używać narzędzia do raportowania elektronicznego do generowania dokumentów biznesowych z osadzonymi obrazami i kształtami.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fe0e6d6def50670566f44cfb5cd6bb4abe5faf15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851056"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Osadzanie obrazów i kształtów w generowanych dokumentach przez raportowanie elektroniczne

[!include [banner](../includes/banner.md)]

Narzędzie Raportowanie elektroniczne (ER) umożliwia projektowanie raportów, które można uruchomić w celu generowania wymaganych dokumentów elektronicznych. Możesz użyć Microsoft Excel lub Microsoft Word, aby określić układ raportu. Projektant operacji ER umożliwia dołączenie dokumentu programu Excel lub Word jako szablonu raportu. Nazwane elementy w dołączonym szablonie są skojarzone z elementami formatu raportu ER. Elementy formatu raportu są powiązane ze źródłami danych. Elementy te określają dane, które zostaną wprowadzone w czasie wykonywania w generowanych dokumentach.

Ta nowa funkcja wykracza poza istniejące możliwości ER do tworzenia dokumentów w formatach Microsoft Office. Aby uzyskać więcej informacji, zapoznaj się z poniższymi przewodnikami po zadaniach. Te przewodniki po zadaniach można znaleźć w procesie biznesowym 7.5.4.3 Pozyskiwanie/opracowywanie składników usług/rozwiązań IT (10677).

- ER Projektowanie konfiguracji do generowania raportów w formacie OPENXML
- Projektowanie ER konfiguracji do generowania raportów w formacie Microsoft WORD

## <a name="embed-an-image-in-an-excel-document"></a>Osadź obraz w dokumencie programu Excel

### <a name="embed-an-image-in-an-excel-worksheet"></a>Osadź obraz w arkuszu programu Excel

Najpierw musisz dodać symbol zastępczy obrazu w dokumencie Excel. Otwórz skoroszyt programu Excel i dodaj obraz jako symbol zastępczy obrazu, który dodasz później. Następnie użyj narzędzia ER, aby dodać nową konfigurację formatu ER, aby uwzględnić projektowany raport. Dołącz skoroszyt programu Excel jako szablon formatu raportu, a następnie zaimportuj zawartość skoroszytu do formatu ER. Definicja formatu zostanie utworzona automatycznie. Dodany symbol zastępczy obrazu zostanie uwzględniony w definicji formatu ER jako element **CELL**.

> [!NOTE]
> Możesz ręcznie określić definicję formatu zamiast ją importować. Zapisanie zmian spowoduje weryfikację formatu.

Następnie powiąż element **CELL** formatu ER z polem ze źródła danych formatu, które dostarcza dane obrazu w formacie binarnym w czasie wykonywania. Jeśli jako źródło danych formatu jest używany model danych ER, typem danych pola musi być [Kontener](er-formula-supported-data-types-composite.md#container). Obecnie pole modelu danych ER, które ma typ danych [Kontener](er-formula-supported-data-types-composite.md#container), może być powiązane z kilkoma typami źródeł danych, które zwracają obrazy w formacie binarnym. Za pomocą struktury zarządzania dokumentami można uzyskać dostęp do pola w tabeli danych i pliku dołączonego do rekordu tabeli danych.

> [!IMPORTANT]
> - Jeśli chcesz wypełnić symbol zastępczy obrazu w tworzonym dokumencie przy użyciu szablonu programu Excel, format ER musi zawierać element **CELL**, który odwołuje się do nazwanego elementu obrazu w szablonie programu Excel. W przeciwnym razie w wyniku raportu nie pojawi się symbol zastępczy obrazu. Jeśli powiązanie elementu **CELL** nie zwróci danych w czasie wykonywania, wygenerowany dokument będzie pokazywał symbol zastępczy obrazu z szablonu. Aby ukryć obraz w dokumencie, który jest wytwarzany, zdefiniuj element **CELL** i określ, że wyrażenie **Włączenie** ma zwracać wartość **FALSE**.
> - W szablonie programu Excel nadaj każdemu elementowi unikatową nazwę. Są to m.in. obrazy i komórki. Jeśli zduplikujesz nazwę elementu, treść wygenerowanego raportu będzie niejednoznaczna i myląca.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Osadź obrazy w nagłówku i stopce arkusza programu Excel

Użyj dokumentu skoroszytu programu Excel jako szablonu, aby określić układ raportu. Skoroszyt może zawierać wiele arkuszy, z których każdy można zaprojektować tak, aby miał nagłówek i stopkę. Program Excel obsługuje maksymalnie trzy obrazy w nagłówku i stopce każdego arkusza. Obraz może być wyrównany do lewej, do prawej lub do środka.

W wersji Finance 10.0.21 można zarządzać obrazami nagłówka i stopki generowanymi przez rozwiązanie ER z szablonem programu Excel.

Jeśli chcesz, aby domyślny obraz był wyświetlany w nagłówku lub stopce wygenerowanego dokumentu, możesz dodać obraz do nagłówka lub stopki arkusza szablonu ER. Aby uzyskać dostęp do tego obrazu w formacie ER, należy dodać składnik **Obraz** w składniku [Nagłówek](er-fillable-excel.md#header-component) lub [Stopka](er-fillable-excel.md#footer-component) formatu. Skonfiguruj wyrównanie składnika **Obraz** zgodnie z potrzebą. 

Można również użyć składnika **Obraz**, aby umieścić obraz w nagłówku lub stopce wygenerowanego dokumentu w czasie wykonywania, nawet jeśli szablon nie zawiera domyślnego obrazu. Aby określić zawartość multimedialną, która powinna zostać umieszczona w nagłówku lub stopce wygenerowanego dokumentu jako nowy obraz lub zamiennik obrazu domyślnego, należy powiązać składnik **Obraz** ze źródłem danych typu [Kontener](er-formula-supported-data-types-composite.md#container), które reprezentuje obraz w formacie binarnym format.

Każdy składnik **nagłówka** lub **stopki** może zawierać jeden składnik **obrazu** dla każdego obsługiwanego wyrównania: do **lewej**, do **środka** i do **prawej**.

Właściwość **Skala wysokości** składnika **Obraz** umożliwia używanie skonfigurowanego powiązania do kontrolowania rozmiaru obrazu:

- Wybierz **Oryginał**, aby zachować początkowy rozmiar obrazu.
- Wybierz opcję **Względna** do skalowania wysokości obrazu proporcjonalnie do wysokości nagłówka lub stopki, która zawiera ten obraz.

    - W takim przypadku wysokość obrazu musi być określona jako procent nagłówka lub stopki nadrzędnego.
    - Jeśli wartość skalowania przekracza 100 procent, obraz może nakładać się na obszar danych odpowiedniego arkusza.
    - Jeśli wysokość obrazu zostanie zmieniona po zastosowaniu skalowania, zmieni się również szerokość, aby zachować oryginalne proporcje obrazu.

- Wybierz opcję **Bezwzględny**, aby zmieniać rozmiar obrazu zgodnie z wartościami wysokości i szerokości (w pikselach) dostarczanymi w czasie projektowania.

    - Jeśli określona wysokość przekracza wysokość nagłówka lub stopki nadrzędnej, obraz może nakładać się na obszar danych odpowiedniego arkusza.

Możesz również użyć właściwości **Włączone** składnika **Obraz**, aby sterować widocznością obrazu, który jest umieszczany w wygenerowanym dokumencie za pomocą tego składnika.

> [!NOTE]
> Aby dodać składnik **obrazu** do edytowalnego formatu ER, należy użyć konstruktora formatu ER. Nie można dodać składnika, gdy do edytowania szablonu dokumentu biznesowego jest używać obszaru roboczego [Zarządzanie dokumentami biznesowymi](er-business-document-management.md).

Aby dowiedzieć się więcej o tej funkcji, wykonaj kroki opisane w temacie [Projektowanie formatu raportu ER, aby wygenerować raport w formacie programu Excel z obrazami osadzonymi w nagłówkach i stopach stron](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Osadź kształt w dokumencie Excel

Najpierw musisz dodać symbol zastępczy kształtu w dokumencie programu Excel. Otwórz skoroszyt programu Excel i wybierz **Kształt**, **Pole tekstowe** lub **WordArt** jako symbol zastępczy kształtu. Następnie użyj narzędzia ER, aby dodać nową konfigurację formatu ER, aby uwzględnić projektowany raport. Dołącz skoroszyt programu Excel jako szablon formatu raportu, a następnie zaimportuj zawartość skoroszytu do formatu ER. Definicja formatu zostanie utworzona automatycznie. Dodany symbol zastępczy kształtu zostanie uwzględniony w definicji formatu raportowania elektronicznego jako element **CELL** odwołujący się do nazwanego elementu kształtu programu Excel.

> [!NOTE]
> Możesz ręcznie określić definicję formatu zamiast ją importować. Zapisanie zmian spowoduje weryfikację formatu.

Następnie powiąż element **CELL** w formacie ER z polem ze źródła danych formatu, które udostępnia dane w czasie wykonywania. Te dane można przekonwertować na ciąg tekstowy. Jeśli element **CELL** w formacie ER odwołuje się do elementu kształtowego w szablonie programu Excel, który obsługuje tekst, tekst dostarczany przez to wiązanie w czasie wykonywania jest wyświetlany w kształtach generowanego dokumentu.

> [!IMPORTANT]
> - Jeśli chcesz użyć szablonu programu Excel zawierającego symbol zastępczy kształtu do wygenerowania nowego dokumentu, format ER musi zawierać element **CELL**, który odwołuje się do elementu kształtu programu Excel. W przeciwnym razie w wyniku raportu nie pojawi się symbol zastępczy kształtu. Jeśli wiązanie elementu **CELL**, który odwołuje się do nazwanego elementu kształtowego programu Excel, nie zwróci danych w czasie wykonywania, generowany dokument będzie zawierał tekst symbolu zastępczego kształtu z szablonu programu Excel. Aby ukryć kształt w dokumencie, który jest wytwarzany, zdefiniuj element **CELL** odwołujący się do nazwanego elementu kształtu Excela i określ, że wyrażenie i określ, że wyrażenie **Włączenie** ma zwracać wartość **FALSE**.
> - W szablonie programu Excel nadaj każdemu elementowi unikatową nazwę. Są to m.in. kształty i komórki. Jeśli zduplikujesz nazwę elementu, treść wygenerowanego raportu będzie niejednoznaczna i myląca.

## <a name="embed-an-image-in-a-word-document"></a>Osadź obraz w dokumencie programu Word
> [!IMPORTANT]
> Możesz ponownie użyć formatu ER, który używa szablonu programu Excel do tworzenia dokumentów zawierających osadzone obrazy. W formacie ER upewnij się, że dla elementu **CELL** określono nazwę, która odwołuje się do nazwanego elementu obrazu w programie Excel i która jest powiązana ze źródłem danych zwracającym obraz w czasie wykonywania.

Najpierw musisz skonfigurować układ dokumentu programu Word. Za pomocą formantu **Zawartość obrazu** utwórz symbol zastępczy dla obrazu osadzonego. Aby uzyskać dostęp do tej kontrolki, najpierw należy udostępnić kartę **Deweloper** na wstążce programu Word.

Następnie usuń szablon programu Excel z formatu ER i dołącz dokument szablonu programu Word. Zaktualizuj odwołanie do szablonu i zapisz zmiany. Struktura bieżącego formatu raportowania elektronicznego jest zapisywana w szablonie programu Word jako nowa niestandardowa część XML o nazwie **Raport**.

Następnie zapisz szablon programu Word dla bieżącego formatu ER na komputerze lokalnym. Otwórz szablon i otwórz okienko **Mapowanie XML**. Znajdź niestandardową część XML o nazwie **Raport**, a następnie wskaż element **CELL** w raporcie ER powiązanym ze źródłem danych, które zwraca obraz w formacie binarnym. Zamapuj element tej części XML na wybraną kontrolę **zawartości obrazu** i zapisz zmiany.

[![osadzać obrazy.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Na koniec usuń szablon programu Word z formatu ER i dołącz dokument programu Word, który zawiera zmapowane niestandardowe części XML. Zaktualizuj odwołanie do formatu do szablonu i zapisz zmiany wprowadzone w tym formacie ER.

## <a name="more-information"></a>Więcej informacji
Aby zapoznać się ze szczegółami tej funkcji, można odtworzyć zestaw przewodników po zadaniach, a także **tworzyć raporty w formatach pakietu MS Office z osadzonymi obrazami**. Te przewodniki po zadaniach pokazują, w jaki sposób można osadzić obrazy logo firmy i podpisu osoby upoważnionej w czekach płatności generowanych za pomocą narzędzia ER w dokumentach programów Excel i Word.

W poniższej tabeli wymieniono pliki wymagane do wykonania zadań **ER Twórz raporty w formatach MS Office z osadzonymi obrazami**. Pobierz i zapisz pliki na komputerze lokalnym.

| opis                                          | Nazwa pliku                   |
|------------------------------------------------------|-----------------------------|
| Konfiguracja modelu danych ER                          | [Model czeków.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER format konfiguracji                              | [Format drukowania czeków.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Obraz logo firmy                                   | [Logo firmy.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Obraz podpisu                                      | [Obraz podpisu.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Alternatywny obraz podpisu                          | [Obraz podpisu 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Szablon programu Microsoft Word do drukowania czeków płatności  | [Szablon czeku Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Szablon programu Microsoft Excel do drukowania czeków płatności | [Szablon czeku.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

Poniższa grafika przedstawia przykład wydruku testowego czeku płatności, który jest generowany z szablonu Excel.

[![Wydruk testu czeku płatności.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
