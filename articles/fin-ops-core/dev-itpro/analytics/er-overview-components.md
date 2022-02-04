---
# required metadata
title: Składniki raportowania elektronicznego
description: W tym temacie opisano składniki raportowania elektronicznego.
author: nselin
ms.date: 09/28/2021
ms.topic: overview
ms.prod: null
ms.technology: null
ms.search.form: ERWorkspace
audience: 'Application User, Developer, IT Pro'
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: '2016-02-28'
ms.dyn365.ops.version: AX 7.0.0
---

# <a name="electronic-reporting-components"></a>Składniki raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Raportowanie elektroniczne (ER) obsługuje następujące typy składników:

- Model danych
- Mapowanie modelu
- Format
- Metadane

## <a name="data-model-component"></a>Składnik modelu danych

Składnik typu Model danych jest abstrakcyjnym przedstawieniem struktury danych. Opisuje konkretny obszar domeny biznesowej wystarczająco szczegółowo, aby spełnić wymagania dotyczące raportowania dla tej domeny. Składnik będący modelem danych zawiera następujące elementy:

- **Model danych** –  jako zestaw jednostek biznesowych określonej domeny oraz hierarchiczna definicja relacji między tymi jednostkami.
- **Mapowanie modelu** – wybrane źródła danych aplikacji są połączone z poszczególnymi elementami modelu danych, który określa w czasie wykonywania przepływ danych i reguły wprowadzania danych biznesowych w składniku modelu danych.

Jednostka biznesowa modelu danych jest reprezentowana jako kontener lub rekord. Właściwości jednostki biznesowej są reprezentowane jako elementy danych lub pola. Każdy element danych ma niepowtarzalną nazwę, etykietę, opis i wartość. Wartość każdego elementu danych można zaprojektować tak, aby była rozpoznawana jako ciąg, liczba całkowita, wartość rzeczywista, data, wyliczenie (wyliczenie) lub wartość logiczna. Dodatkowo element danych może być innym rekordem lub listą rekordów.

Pojedynczy składnik typu Model danych może zawierać kilka hierarchii jednostek biznesowych właściwych dla danej domeny. Może również zawierać mapowania modelu obsługujące przepływ danych właściwy dla raportu w czasie wykonywania. Hierarchie są rozróżniane przez pojedynczy rekord, który został wybrany jako główny dla mapowania modelu. Na przykład model danych obszaru domeny płatności może obsługiwać następujące mapowania:


- Firma \> Dostawca \> Transakcje płatności w przypadku domeny rozrachunków z dostawcami
- Odbiorca \> Firma \> Transakcje płatności w przypadku domeny rozrachunków z odbiorcami

Podmioty gospodarcze, takie jak transakcje firmowe i płatnicze, są projektowane tylko raz. W razie potrzeby można używać ich ponownie w różnych mapowaniach.

## <a name="model-mapping-component"></a>Składnik mapowania modelu

Mapowanie modelu łączy źródła danych aplikacji z poszczególnymi elementami modelu danych, które określają w czasie wykonywania przepływ danych i reguły wprowadzania danych biznesowych w składniku modelu danych.

Mapowanie modelu obsługujące wychodzące dokumenty elektroniczne ma następujące możliwości:

- Może wykorzystywać różne typy danych jako źródła danych dla modelu danych. Te typy danych obejmują tabele, jednostki danych, metody i wyliczenia.
- Obsługuje parametry wejściowe użytkownika, które można zdefiniować jako źródła danych modelu danych, gdy część danych musi być określona w czasie wykonywania.
- Obsługuje transformację danych do wymaganych grup. Umożliwia także filtrowanie, sortowanie i sumowanie danych, a także dołączanie logicznych pól obliczanych, które są projektowane za pomocą formuł przypominających formuły programu Microsoft Excel. Aby uzyskać więcej informacji, zobacz [Projektant formuł w raportowaniu elektronicznym (ER)](general-electronic-reporting-formula-designer.md).

Mapowanie modelu obsługujące przychodzące dokumenty elektroniczne ma następujące możliwości:

- Może używać różnych aktualizowanych elementów danych jako celów. Te elementy danych obejmują tabele, jednostki danych i widoki. Dane można aktualizować o dane przychodzące z dokumentów elektronicznych. W jednym mapowaniu modelu można użyć wielu elementów docelowych.
- Obsługuje parametry wejściowe użytkownika, które można zdefiniować jako źródła danych modelu danych, gdy część danych musi być określona w czasie wykonywania.

Komponent modelu danych jest przeznaczony dla każdej domeny biznesowej używanej jako ujednolicone źródło danych do raportowania. Ujednolicone źródło danych izoluje raportowanie od fizycznej implementacji źródeł danych. Składnik reprezentuje właściwe dla domeny koncepcje i funkcje biznesowe w formie, która upraszcza początkowe projektowanie formatów raportowania i ich dalszą obsługę.

## <a name="format-component"></a>Składnik formatu

### <a name="format-components-for-outgoing-electronic-documents"></a>Składniki typu Format dla wychodzących dokumentów elektronicznych

Składnik typu Format określa schemat danych wyjściowych raportowania, które jest generowane w czasie wykonywania. Schemat składa się z następujących elementów:

- Format definiujący strukturę i zawartość wychodzącego dokumentu elektronicznego generowanego podczas wykonywania.
- Źródła danych jako zestaw parametrów wejściowych użytkownika i modelu danych właściwego dla domeny, który wykorzystuje wybrany model mapowania.
- Mapowanie formatu jako zestaw powiązań źródeł danych formatu zawierających poszczególne elementy formatu, które podczas wykonywania określają przepływ danych i reguły generowania danych wyjściowych w tym formacie.
- Sprawdzanie poprawności formatu jako zestaw konfigurowalnych reguł sterujących generowaniem raportu w czasie wykonywania w zależności od kontekstu pracy. Na przykład może istnieć reguła, która zatrzymuje generowanie danych wyjściowych płatności dla dostawcy i zgłasza wyjątek, gdy brakuje określonych atrybutów wybranego dostawcy, takich jak numer konta bankowego.

Składnik typu Format obsługuje następujące funkcje:

- Tworzenie danych wyjściowych raportowania jako pojedynczych plików w różnych formatach, takich tekstowy, XML, dokument programu Microsoft Word lub arkusz
- Tworzenie wielu plików osobno i zamykanie ich w plikach zip

Składnik typu Format umożliwia załączanie określonych plików, które mogą być używane w wynikach raportowania:

- Skoroszyty programu Excel zawierające arkusze, których można używać jako szablonów danych wyjściowych w formacie arkusza OPENXML.
- Pliki programu Word zawierające dokumenty, których można używać jako szablonów danych wyjściowych w formacie dokumentów programu Microsoft Word.
- Inne pliki, które mogą zostać włączone w dane wyjściowe formatu jako pliki wstępnie zdefiniowane.

Na poniższej ilustracji przedstawiono sposób przepływu danych w tych formatach.

[![Przepływ danych dla składników typu Format dokumentów przychodzących.](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Aby uruchomić jedną konfigurację formatu modułu ER w celu zaimportowania danych z przychodzącego dokumentu elektronicznego, należy określić żądane mapowanie konfiguracji formatu oraz punkt integracji mapowania modelu. Tego samego mapowania modelu i miejsc docelowych można używać w połączeniu z różnymi formatami dla różnych rodzajów dokumentów przychodzących.

## <a name="component-versioning"></a>Przechowywanie wersji składnika

Dla składników ER jest obsługiwane przechowywanie wersji. Poniższy przepływ pracy służy do zarządzania zmianami w składnikach ER:

1. Wersja tworzona pierwotnie jest oznaczona jako **Wersja robocza**. Ta wersja może być edytowana i jest dostępna do testów.
2. Wersję **Wersja robocza** można przekonwertować na wersję **Ukończona**. Ta wersja może być używana w lokalnych procesach raportowania.
3. Wersję **Ukończona** można przekonwertować na wersję **Udostępniona**. Ta wersja jest publikowana w usłudze  Microsoft Dynamics Lifecycle Services LCS i może być używana w globalnych procesach sprawozdawczości.
4. Wersję **Udostępniona** można przekonwertować na wersję **Wycofana**. Tę wersję można następnie usunąć.

Wersje ze stanem **Ukończona** lub **Udostępniona** są dostępne dla innych procesów wymiany danych. Na składniku mającym te stany można wykonywać następujące operacje:

- Składnik może być serializowany w formacie XML i eksportowany jako plik w formacie XML.
- Składnik może być reserializowany z pliku XML i importowany do aplikacji jako nowa wersja składnika raportowania elektronicznego.

## <a name="component-date-effectivity"></a>Daty obowiązywania składnika

Wersje składników ER mają daty obowiązywania. Można ustawić datę wejścia w życie dla składnika ER, aby określić datę, od której składnik zacznie obowiązywać w procesach raportowania. Data sesji aplikacji pozwala określić, czy składnik może być uruchamiany. Gdy dla danej daty jest dostępnych kilka wersji, najnowsza wersja jest używana w procesach raportowania.

## <a name="component-access"></a>Dostęp do składnika

Dostęp do składników formatu ER zależy od ustawienia kodu kraju/regionu Międzynarodowej Organizacji Normalizacyjnej (ISO). Gdy to ustawienie jest puste dla wybranej wersji konfiguracji formatu, dostęp do składnika formatu można uzyskać podczas wykonywania z każdej firmy. Gdy to zawiera kody ISO kraju/regionu, składnik formatu jest dostępny tylko z tych firm, których adres główny został zdefiniowany dla jednego z kodów ISO kraju/regionu istniejących w składniku formatu.

Różne wersje składnika formatu danych mogą mieć różne ustawienia kodów ISO kraju/regionu.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

