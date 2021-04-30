---
title: Konfigurowanie źródeł danych wyszukiwania do używania parametrów specyficznych dla raportowania elektronicznego
description: W tym temacie wyjaśniono, jak skonfigurować źródła danych wyszukiwania w formatach raportowania elektronicznego (ER), aby używać parametrów specyficznych dla aplikacji ER.
author: NickSelin
manager: AnnBe
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 542580c859759c25da84589ec82495eb72bbcbe5
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853528"
---
# <a name="configure-lookup-data-sources-to-use-er-application-specific-parameters"></a>Konfigurowanie źródeł danych wyszukiwania do używania parametrów specyficznych dla raportowania elektronicznego 

[!include[banner](../includes/banner.md)]

Funkcja parametrów specyficznych dla aplikacji [Raportowanie elektroniczne (ER)](general-electronic-reporting.md) umożliwia użytkownikom zaawansowanym konfigurowanie filtrowania danych w formacie ER, tak aby były oparte na zbiorze reguł abstrakcyjnych. Ten zestaw reguł można skonfigurować tak, aby używał źródła danych typu **Wyszukiwanie**, które jest dostępne w formacie ER. Następnie można określić rzeczywiste reguły wykraczające poza projektantów komponentów ER, korzystając z interfejsu użytkownika (UI), który jest generowany automatycznie na podstawie ustawień źródła danych **Wyszukiwanie** odpowiedniego formatu ER i bieżących danych podmiotu prawnego. Po wykonaniu tego formatu ER określone reguły będą dostępne w źródle danych **Wyszukiwanie** formatu ER.

> [!NOTE]
> Skorzystaj ze skonfigurowanych źródeł danych w edytowalnym formacie ER, aby określić, które dane aplikacji są używane do konfigurowania rzeczywistych reguł.

Za pomocą [projektanta Operacji ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) można wprowadzić źródło danych typu **Wyszukiwanie** do formatu ER. Źródło danych należy skonfigurować tak, aby opisywało wygląd reguł abstrakcyjnych, w tym:

   - Zestaw parametrów określonego typu danych, którego wartość jest dostarczana w celu określenia jednej reguły.
   - Typ wartości określonego typu danych zwracany przez pojedynczą regułę, gdy ta reguła jest uważana za najbardziej odpowiednią między innymi.

Możesz skonfigurować następujące typy źródeł danych **Wyszukiwanie** w zależności od typu wartości zwracanej przez dowolną skonfigurowaną regułę:

   - Użyj typu **Model danych\Wyszukiwanie**, gdy musi zostać zwrócona wartość wyliczenia modelu.
   - Użyj typu **Dynamics 365 Operations\Wyszukiwanie**, gdy musi zostać zwrócona wartość wyliczenia aplikacji lub wartość [rozszerzonego typu danych aplikacji](../extensibility/extensible-edts.md).
   - Użyj typu **Wyliczenie formatów\Wyszukiwanie**, gdy musi zostać zwrócona wartość wyliczenia formatów.

Na poniższej ilustracji pokazano, jak można skonfigurować wyliczenie formatów w przykładowym formacie ER.

   ![Wyświetlanie wyliczenia formatów jako podstawy skonfigurowanego źródła danych wyszukiwania](./media/er-lookup-data-sources-img1.gif)

Na poniższej ilustracji przedstawiono składniki formatu skonfigurowane do zgłaszania różnych typów podatków w innej sekcji generowanego raportu.

   ![Wyświetlanie sekcji formatu osobno raportujących różne typy podatków](./media/er-lookup-data-sources-img2.png)

Na poniższej ilustracji pokazano, w jaki sposób projektant ER Operations umożliwia dodanie źródła danych **Wyliczenie formatów\Wyszukiwanie**.  Dodane źródło danych jest skonfigurowane jako zwracające wartość wyliczenia formatów `List of taxation levels`.

   ![Dodawanie źródła danych ER wyliczenia formatów\wyszukiwania](./media/er-lookup-data-sources-img3.gif)

Na poniższej ilustracji pokazano, w jaki sposób dodano źródło danych skonfigurowane do używania pola **Kod** z listy rekordów **Model.Data.Tax** źródła danych **modelu** jako parametru, który należy określić dla każdej skonfigurowanej reguły.

![Konfigurowanie parametrów dodanego źródła danych typu Wyliczenie formatu \ Wyszukiwanie](./media/er-lookup-data-sources-img4.gif)

Dodane źródło danych `Model.Data.Tax` jest skonfigurowane tak, aby określać kod podatku dla każdej skonfigurowanej reguły, uzyskując dostęp do rekordów tabeli aplikacji **TaxTable**.

   ![Przegląd źródła danych wyszukiwania dla pojedynczej firmy typu Wyliczenie formatu \ Wyszukiwanie](./media/er-lookup-data-sources-img5.gif)

Reguły wyszukiwania dla wybranego formatu ER można skonfigurować za pomocą interfejsu użytkownika, który jest automatycznie dopasowywany do struktury skonfigurowanego źródła danych. Obecnie ten interfejs użytkownika wymaga, aby dla każdej reguły określić zwracaną wartość jako wartość wyliczenia w formacie `List of taxation levels`, a także kod podatku jako parametr.

   ![Umożliwia ustawianie reguł dla skonfigurowanego źródła danych](./media/er-lookup-data-sources-img6.gif)

Na poniższej ilustracji pokazano, jak źródło danych `Model.Data.Summary.LevelByLookup` typu **Pole obliczeniowe** można skonfigurować tak, aby wywoływało skonfigurowane źródło danych **Wyszukiwanie** z wymaganymi parametrami. Aby przetworzyć to wywołanie w czasie wykonywania, ER przegląda listę skonfigurowanych reguł w zdefiniowanej kolejności, aby zlokalizować pierwszą regułę, która spełnia podane warunki. W tym przykładzie jest to reguła zawierająca kod podatku, który pasuje do podanego kodu. W związku z tym znaleziono najo odpowiednią regułę, a wartość wyliczenia skonfigurowana dla znalezionej reguły jest zwracana przez to źródło danych.

> [!NOTE]
> Wystąpił wyjątek, gdy nie znaleziono właściwej reguły. Aby zapobiec tym wyjątkom, skonfiguruj dodatkowe reguły na końcu listy reguł, aby obsługiwały przypadki, gdy nie została podana nieskonfigurowana wartość lub żadna wartość nie została podana. Użyj odpowiednio opcji **\*Niepuste\*** i **\*Puste\***.  
>
> ![Dodaj źródło danych, aby wywołać skonfigurowane źródło danych wyszukiwania](./media/er-lookup-data-sources-img7.png)

W przypadku ustawienia opcji **Między firmami** na wartość **Tak** dla edytowalnego źródła danych wyszukiwania należy dodać nowy wymagany parametr **Firma** do zestawu parametrów tego źródła danych. Podczas wywoływania źródła danych wyszukiwania należy określić wartość parametru **Firma** w czasie wykonywania. Gdy kod firmy jest określony w czasie wykonywania, reguły skonfigurowane dla tej firmy są używane do znalezienia najbardziej odpowiedniej reguły i zwracana jest odpowiednia wartość. Poniższa ilustracja przedstawia, jak można to zrobić i jak zmienia się zestaw parametrów edytowalnego źródła danych.

   ![Przejrzyj źródło danych wyszukiwania międzyfirmowego typu Wyliczenie formatu \ Wyszukiwanie](./media/er-lookup-data-sources-img8.gif)

> [!NOTE]
> Wybierz każdą firmę oddzielnie, aby skonfigurować zestaw reguł dla tego źródła danych wyszukiwania w edytowalnym formacie ER. Wyjątek jest generowany w czasie wykonywania, gdy wyszukiwanie międzyfirmowe jest wywoływane z kodem firmy, dla której ustawienie wyszukiwania nie zostało zakończone.
>
> Upewnij się, że masz uprawnienia użytkownika, który uruchamia format ER za pomocą między firmowego źródła danych **wyszukiwania**, do dostępu do danych każdej firmy, która znajduje się w zakresie tego źródła danych. W przeciwnym razie wyjątek jest zgłaszany w czasie wykonywania.

Począwszy od wersji 10.0.19 są dostępne rozszerzone możliwości źródeł danych **Wyszukiwania**. Po skonfigurowaniu opcji **Rozszerzone** na wartość **Tak** dla edytowalnego źródła danych wyszukiwania skonfigurowane źródło danych wyszukiwania zostanie przekształcone w strukturalne źródło danych, które oferuje dodatkowe możliwości analizowania skonfigurowanego zestawu reguł. Poniższa ilustracja przedstawia tę transformację.

   ![Przegląd źródła danych wyszukiwania strukturalnego typu Wyliczenie formatu \ Wyszukiwanie](./media/er-lookup-data-sources-img9.gif)

- Pozycja podrzędna **Wyszukiwanie** została zaprojektowana jako funkcja znajdująca najbardziej odpowiednią regułę ze zbioru konfigurowalnych reguł w oparciu o dostarczony zestaw parametrów.
- Element podrzędny **IsLookupResultSet** jest przeznaczony do akceptowania podanej wartości źródła danych wyliczenia podstawowego i zwracania wartości *logicznych* **True**, jeśli zestaw reguł zawiera co najmniej jedną regułę, dla której dostarczana wartość wyliczenia została skonfigurowana jako zwracana wartość. Ta funkcja zwraca wartość *logiczną* **False**, jeśli nie skonfigurowano reguł zwracania podanej wartości wyliczenia.
- Pozycja podrzędna **Ustawienie** została zaprojektowana jako funkcja zwracająca zestaw skonfigurowanych reguł jako rekordy listy rekordów. Zwracane wartości i zestaw parametrów skonfigurowanych reguł prezentowane są w każdym zwracanym rekordzie jako pola odpowiednich typów danych:

    - Zwracana wartość jest prezentowana jako pole **Wynik wyszukiwania**.
    - Skonfigurowane parametry są prezentowane jako pola mające nazwy parametrów (pole **Kod** w tym przykładzie).

Aby uzyskać więcej informacji dotyczących konfigurowania źródła danych **wyszukiwania**, zobacz temat [Konfiguracja formatów raportowania elektronicznego do używania parametrów określonych dla firmy](er-app-specific-parameters-configure-format.md). Aby się dowiedzieć, jak skonfigurować reguły wyszukiwania, zobacz temat [Konfiguracja parametrów formatu raportowania elektronicznego dla firmy](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguracja formatów raportowania elektronicznego do używania parametrów określonych dla firmy](er-app-specific-parameters-configure-format.md)

[Konfiguracja parametrów formatu raportowania elektronicznego dla firmy](er-app-specific-parameters-set-up.md)
