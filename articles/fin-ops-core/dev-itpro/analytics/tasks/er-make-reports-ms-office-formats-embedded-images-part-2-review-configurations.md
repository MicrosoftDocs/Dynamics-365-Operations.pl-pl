---
title: Przeglądanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami
description: W tym artykule opisano sposób projektowania konfiguracji generujących dokumenty elektroniczne z osadzonymi obrazami. (część 1 — konfigurowanie parametrów).
author: kfend
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12f7b9b027506657809dc9fa50cf97a0300a5310
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290313"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>Przeglądanie konfiguracji służących do generowania raportów w formatach pakietu Office z osadzonymi obrazami

[!include [banner](../../includes/banner.md)]

Aby wykonać te kroki, należy najpierw wykonać kroki z przewodnika po zadaniu „ER Tworzenie raportów w formatach programu MS Office z osadzonymi obrazami (Część 1: Konfigurowanie parametrów)”.

W tej procedurze pokazano sposób projektowania konfiguracji raportowania elektronicznego (ER) do generowania dokumentów elektronicznych z osadzonymi obrazami w programach Microsoft Excel i Microsoft Word. W tym przykładzie przejrzysz konfiguracje ER przykładowej firmy Litware, Inc. 

Ta procedura jest przeznaczona dla użytkowników z przypisaną rola Administrator systemu lub Deweloper raportowania elektronicznego. Kroki można wykonać przy użyciu zestawu danych firmy USMF.


## <a name="review-the-imported-data-model"></a>Przeglądanie zaimportowanego modelu danych
1. Wybierz kolejno opcje Administrowanie organizacją > Raportowanie elektroniczne > Konfiguracje.
2. W drzewie zaznacz element „Model czeków”.
3. Kliknij przycisk Konstruktor.
    * Ten model jest przeznaczony do reprezentowania czeków płatniczych z biznesowego punktu widzenia oraz do mapowanie tego modelu na źródła danych aplikacji. Model musi zostać przejrzany przez projektanta operacji raportowania elektronicznego. Należy zwrócić uwagę na atrybuty prezentowanych elementów modelu: struktura, nazwa, opis, typ danych i tak dalej.   
4. W drzewie rozwiń węzeł „katalog główny”.
5. W drzewie zaznacz element „katalog główny\czeki”.
6. W drzewie rozwiń węzeł „katalog główny\czeki”.
7. W drzewie rozwiń węzeł „katalog główny\czeki\atrybuty”.
8. W drzewie rozwiń węzeł „katalog główny\płatnik”.
9. W drzewie zaznacz element „katalog główny\istestrun”.
10. W drzewie zaznacz element „katalog główny\układ”.
    * Element układu tego modelu reprezentuje szczegóły układu formularza drukowania czeków dla wybranego konta bankowego. Zawiera także dwa węzły danych typu Kontener do przechowywania obrazów.   
11. W drzewie rozwiń węzeł „katalog główny\układ”.
12. W drzewie zaznacz element „katalog główny\układ\logo firmy”.
13. W drzewie rozwiń węzeł „katalog główny\układ\logo firmy”.
14. W drzewie zaznacz element „katalog główny\układ\logo firmy\obraz”.
15. W drzewie zaznacz element „katalog główny\układ\logo firmy\isprinted”.
16. W drzewie zaznacz element „katalog główny\układ\podpis”.
17. W drzewie rozwiń węzeł „katalog główny\układ\podpis”.
18. W drzewie zaznacz element „katalog główny\układ\podpis\obraz”.
19. W drzewie zaznacz element „katalog główny\układ\podpis\isprinted”.
    * Należy zauważyć, że dwa elementy modelu danych obrazu są powiązane z polami tabel zawierających obrazy logo firmy i podpisu osoby upoważnionej osoby w formacie binarnym.  
20. W drzewie rozwiń węzeł „katalog główny\układ\znak wodny”.
21. Kliknij opcję Mapuj model na źródło danych.
22. Kliknij przycisk Konstruktor.
23. W drzewie rozwiń węzeł „chequesselected”.
24. W drzewie rozwiń węzeł „układ”.
25. W drzewie rozwiń węzeł „układ\logo firmy”.
26. W drzewie rozwiń węzeł „układ\podpis”.
27. W drzewie rozwiń węzeł „układ\znak wodny”.
28. Włącz opcję „Pokaż szczegóły”.
    * Należy zauważyć, że element modelu danych czeków jest powiązany z tabelą TmpChequePrintout, która w czasie wykonywania będzie zawierała rekordy czeków wybranych przez użytkownika do drukowania.   
29. Zamknij stronę.
30. Zamknij stronę.
31. Zamknij stronę.

## <a name="review-the-imported-format"></a>Przeglądanie zaimportowanego formatu
1. W drzewie rozwiń węzeł „Model czeków”.
2. W drzewie zaznacz element „Model czeków\Format drukowania czeków”.
3. Kliknij przycisk Konstruktor.
4. Kliknij opcję Załączniki.
5. Kliknij przycisk Otwórz.
    * Otwórz szablon dołączonego raportu w programie Excel.  
    * Przejrzyj szablon programu Excel dołączonego raportu, który będzie używany do drukowania czeków. Szablon zawiera dwa czeki na każdej stronie i jest przeznaczony do drukowania czeków na formularzu z nadrukiem. Należy zauważyć, że dwa puste obrazy są osadzone. Te puste obrazy są przeznaczone na logo firmy i podpis osoby, która autoryzuje płatność. Upewnij się, że w programie Excel obrazy mają nazwy odpowiednio CompLogo i SignatureImage.   
6. Zamknij stronę.
7. W drzewie rozwiń węzeł „Raport”.
8. W drzewie rozwiń węzeł „Raport\ChequeLines”.
9. W drzewie zaznacz element „Raport\ChequeLines\CompLogo”.
10. Włącz opcję „Pokaż szczegóły”.
    * Należy zwrócić uwagę, że element komórki formatu „CompLogo” reprezentuje element programu Excel, który jest używany do wypełniania obrazu logo firmy w raporcie. Ten element formatu jest powiązany z elementem modelu danych obrazu, który w czasie wykonywania zawiera obraz logo firmy w formacie binarnym.   
11. Kliknij kartę Mapowanie.
12. Kliknij opcję Edycja włączona.
    * Należy zwrócić uwagę, że element komórki formatu „CompLogo” można skonfigurować tak, aby przestał być włączony. W takim przypadku skojarzony element obrazu programu Excel będzie ukrywał logo firmy w wygenerowanym raporcie. Jeśli włączone wyrażenie zwraca wartość TRUE, a zdefiniowane wiązanie nie powoduje zwracania obrazu, skojarzony element obrazu programu Excel wyświetli obraz, który został zapisany w szablonie programu Excel.   
13. Zamknij stronę.
14. W drzewie rozwiń węzeł „etykiety: Kontener”.
    * Niektóre etykiety prezentowane w formularzu czeku z nadrukiem zostaną uwzględnione w raporcie podczas jego tworzenia do celów testowych. Jednak te etykiety nie będą drukowane podczas rzeczywistego drukowania, ponieważ formularz z nadrukiem już je zawiera.  
15. Zamknij stronę.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
