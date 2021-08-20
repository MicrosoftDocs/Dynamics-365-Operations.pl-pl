---
title: Konfigurowanie magazynu przy użyciu szablonu konfiguracji magazynu
description: W tym temacie wyjaśniono sposób konfigurowania magazynu przy użyciu szablonu konfiguracji magazynu.
author: perlynne
ms.date: 11/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: adb14507ad26879ee4811c6eb984ce3888b1913a0e6f0664a99079ba49f1a4c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751920"
---
# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a>Konfigurowanie magazynu przy użyciu szablonu konfiguracji magazynu

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania magazynu przy użyciu szablonu konfiguracji magazynu. Dostępnych jest kilka wstępnie zdefiniowanych szablonów konfiguracji, których można użyć. Aby uzyskać informacje na temat korzystania z tych szablonów, zobacz [Szablony danych konfiguracji](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a>Scenariusze, w których przydatne są szablony konfiguracji

Szablony konfiguracji przydają się w wielu scenariuszach. Oto kilka przykładów:

- Ukończono i przetestowano ustawienia konfiguracji w środowisku testowym i chcesz teraz skopiować konfigurację w środowisku produkcyjnym.
- Chcesz wdrożyć konfigurację magazynu w kilku firmach lub utworzyć nowy magazyn w tej samej firmie.
- Chcesz szybko przygotować demonstrację funkcji magazynu.
- Chcesz, aby istniejące towary i magazyny używały funkcji w module Zarządzanie magazynem zamiast funkcji w module Zarządzanie zapasami.

Ten temat dotyczy pierwszego z tych scenariuszy. Pokazuje, jak można użyć szablonu konfiguracji do skopiowania ustawień konfiguracji ze środowiska testowego do środowiska produkcyjnego.

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a>Kopiowanie ustawień konfiguracji ze środowiska testowego do środowiska produkcyjnego

W tym scenariuszu ustawienia konfiguracji dla magazynu i niektórych procesów transakcji już istnieją w środowisku testowym. Chcesz skopiować ustawienia konfiguracji magazynu ze środowiska testowego do środowiska produkcyjnego.

> [!NOTE]
> W przypadku kopiowania ustawień konfiguracji należy pamiętać o uwzględnieniu innych powiązanych danych konfiguracji. Przykładowo, chcesz skonfigurować produkty, kopiując konfigurację ze środowiska testowego. Jednakże nie możesz skonfigurować stałej lokalizacji pobrania dla produktu przed jego utworzeniem. Mimo że poszczególne szczegóły konfiguracji nie obsługują tego typu zależności, istnieją domyślne szablony danych, które umożliwiają taką obsługę. Można łatwo dodać te domyślne szablony danych do procesu konfiguracji.

### <a name="export-a-default-warehouse-template"></a>Eksportowanie domyślnego szablonu magazynu 

1. Otwórz obszar roboczy **Zarządzanie danymi**.

    > [!NOTE]
    > Jeżeli korzystasz z tego obszaru roboczego po raz pierwszy, przed kontynuacją musisz załadować wszystkie jednostki danych.

2. Wybierz kafelek **Szablony**, a następnie wybierz opcję **Załaduj szablony domyślne**, aby załadować szablony domyślne.

    > [!NOTE]
    > Opcja **Załaduj szablony domyślne** jest dostępna tylko w widoku **Rozszerzony**. Wybierz opcję **Parametry struktury**, a następnie w polu **Wyświetl ustawienia domyślne** wybierz opcję **Widok rozszerzony**.

3. Po załadowaniu szablonów domyślnych można je zmienić tak, aby spełniały wymagania firmy.

    > [!NOTE]
    > Aby załadować szablony domyślne i zaimportować je, wymagany jest dostęp na poziomie administratora systemu. To wymagania pozwala zapewnić prawidłowe załadowanie wszystkich jednostek do szablonu.

4. Sprawdź, czy wybrano firmę, z której chcesz wyeksportować dane specyficzne dla firmy.
5. W obszarze roboczym wybierz opcję **Eksportuj**.
6. Utwórz nowy projekt eksportu.
7. Wybierz opcję **+ Dodaj szablon** i znajdź szablon domyślny magazynu **400 - WMS**. Ten szablon umożliwia dodanie jednostek danych dla konfiguracji magazynu.

    > [!NOTE]
    > Jeżeli eksportowane dane muszą zostać odfiltrowane (przykładowo, chcesz wyeksportować tylko dane związane z określonym magazynem), należy ocenić każdą jednostkę danych i dodać filtrowanie za pomocą kwerendy. Można też wyeksportować wszystkie dane, a następnie usunąć niepotrzebne rekordy w plikach docelowych.

8. Wybierz opcję **Eksportuj**. Zostaną wyeksportowane dane dotyczące wszystkich jednostek danych w projekcie.

Można pobrać plik zip pakietu danych. Ten plik zawiera wszystkie dane w wybranym formacie (na przykład w formacie programu Excel). Jak wspomniano wcześniej, niektóre rekordy w plikach pakietu danych mogą wymagać aktualizacji przed zaimportowaniem ich do środowiska produkcyjnego. Jeżeli aktualizujesz rekord, nie zmieniaj nazwy pliku.

### <a name="import-a-warehouse-configuration-setup"></a>Importowanie ustawień konfiguracji magazynu

1. W środowisku docelowym upewnij się, że wybrano firmę, do której chcesz zaimportować dane magazynu.

    > [!NOTE]
    > Przed rozpoczęciem importu należy zidentyfikować wszystkie zależności danych. Przykładowo, szablon **Zarządzanie magazynem** zawiera jednostkę danych o nazwie **Kody dyspozycji z magazynu**. Ta jednostka zawiera dane dotyczące strony konfiguracji **Kody dyspozycji** (**Zarządzanie magazynem** > **Konfiguracja** > **Urządzenie przenośne** > **Kody dyspozycji**). Jeżeli istniejąca konfiguracja obsługuje już proces zwrotu zamówień sprzedaży pole **Zwróć kod dyspozycji** zawiera wartość. Kod dyspozycji w tym polu dotyczy jednostki danych **Kod dyspozycji**, która jest częścią szablonu **Sprzedaż i marketing**. Jeżeli dane z jednostki danych **Kod dyspozycji** nie zostaną zaimportowane przed danymi z pola **Kody dyspozycji z magazynu**, import nie powiedzie się.

2. W obszarze roboczym **Zarządzanie danymi** wybierz opcję **Importuj**.
3. Utwórz nowy projekt importu.
4. Wybierz opcję **+ Dodaj plik** i przekaż plik zip pakietu danych.
5. Wybierz opcję **Importuj**. W widoku **Rozszerzony** można użyć opcji **Filtr**, aby szybko uzyskać przegląd problemów, które mogą wystąpić podczas importu.

Opcja **Wyświetl dziennik wykonywania** umożliwia uzyskanie szczegółowych informacji o każdej importowanej jednostce danych. Aby szybko pobrać dane docelowe, można użyć widoku danych pośrednich. Umożliwia to sprawdzenie wyglądu zaimportowanych danych na powiązanych stronach w aplikacji. Jeżeli używane są szablony danych domyślnych, sekwencja importu dla każdej jednostki danych działa we wstępnie zdefiniowany sposób, aby zapewnić, że najpierw zostaną zaimportowane wszystkie dane zależne. Jeżeli częścią projektu są niestandardowe jednostki danych, należy zdefiniować prawidłową sekwencję. Aby uzyskać więcej informacji, zobacz temat [Szablony danych konfiguracji](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md).

Aby uzyskać więcej informacji na temat sposobu korzystania z szablonu magazynu do skopiowania konfiguracji magazynu z jednej firmy do nowej firmy w tym samym wystąpieniu, zobacz ten 3 minutowy film w serwisie YouTube o [sposobie użycia szablonu magazynu służy do kopiowania konfiguracji w Finance and Operations](https://www.youtube.com/watch?v=K2WIfFlqJYs).

## <a name="related-topic"></a>Powiązany temat

[Szablony danych konfiguracji](../../fin-ops-core/dev-itpro/data-entities/configuration-data-templates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]