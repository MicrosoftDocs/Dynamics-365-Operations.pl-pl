---
title: Kompresuj duże dokumenty generowane w ramach raportowania elektronicznego
description: W tym temacie opisano sposób kompresowania dużych dokumentów generowanych przez format modułu raportowanie elektroniczne (ER).
author: NickSelin
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 899af54fbe34841c9b9b6e96b78db96773cf0203
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894179"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Kompresuj duże dokumenty generowane w ramach raportowania elektronicznego 

[!include [banner](../includes/banner.md)]

Możesz użyć [Struktury raportowania elektronicznego (ER)](general-electronic-reporting.md), aby skonfigurować rozwiązanie, które pobiera dane transakcyjne w celu wygenerowania dokumentu wychodzącego. Wygenerowany dokument może być dość duży. Po wygenerowaniu tego typu dokumentu używana jest pamięć [Application Object Server (AOS)](../dev-tools/access-instances.md#location-of-packages-source-code-and-other-aos-configurations). W pewnym momencie dokument musi zostać pobrany z aplikacji Microsoft Dynamics 365 Finance. Obecnie maksymalny rozmiar pojedynczego dokumentu wygenerowanego w module ER jest ograniczony do 2 gigabajtów (GB). Ponadto Finance [ograniczają](https://fix.lcs.dynamics.com/Issue/Details?kb=4569432&bugId=453907&dbType=3) obecnie rozmiar pobranego pliku do 1 GB. Dlatego należy skonfigurować rozwiązanie ER, które zmniejsza prawdopodobieństwo, że te ograniczenia zostaną przekroczone i że zostanie wyświetlony wyjątek **Strumień był zbyt długi** lub **Przepełnienie lub niedomiar w operacji arytmetycznej**.

Podczas konfigurowania rozwiązania można dostosować format ER w Projektancie operacji, dodając element główny typu **Folder**, aby skompresować zawartość generowaną przez dowolny z jego zagnieżdżonych elementów. Kompresja działa „w samą porę”, dzięki czemu maksymalne zużycie pamięci i rozmiar pobieranego pliku można zmniejszyć.

> [!NOTE]
> Kompresja plików zajmuje dodatkowy procent wykorzystania procesora.

Aby uzyskać więcej informacji o tym podejściu, uzupełnij przykład w tym temacie.

## <a name="example-compress-an-outbound-document"></a>Przykład: kompresowanie dokumentu wychodzącego

W tym przykładzie przedstawiono sposób, w jaki użytkownik przypisany do roli **Administrator systemu** lub **Konsultant funkcjonalny raportowania elektronicznego** może skonfigurować format ER w celu skompresowania wygenerowanego dokumentu.

### <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem procedur opisanych w tym temacie należy wykonać następujące kroki.

1. [Aktywuj dostawcę konfiguracji](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importuj przykładowe konfiguracje ER](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Przeglądanie zaimportowanego formatu](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> Obecnie struktura formatu rozpoczyna się od elementu **Raport** typu **Plik** i zawiera elementy XML. Z tego powodu dokument wychodzący zostanie wygenerowany w formacie XML i nie zostanie użyta kompresja.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Generowanie formatu ER w celu uzyskania nieskompresowanego dokumentu

1. [Uruchamianie zaimportowanego formatu](er-defer-xml-element.md#run-the-imported-format).
2. Zauważ, że rozmiar wygenerowanego dokumentu w formacie XML wynosi 3 kilobajty (KB).

    ![Podgląd nieskompresowanego dokumentu wychodzącego](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Zmodyfikuj format, aby skompresować wygenerowany wynik

1. Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Model do nauki elementów odłożonych**.
3. Wybierz konfigurację **Format do nauki odłożonych elementów XML**.
4. Wybierz opcję **Projektant**, aby zmienić strukturę formatu.
5. Na stronie **Projektant formatów** na karcie **Format** wybierz **Dodaj źródło**, aby dodać element główny formatu.
6. W oknie dialogowym **Dodaj** wybierz opcję **Wspólny\\Folder**.
7. Wybierz przycisk **OK**, aby potwierdzić dodanie nowego elementu główny.
8. Wybierz opcję **Zapisz**.

> [!NOTE]
> Struktura formatu zaczyna się od elementu typu **Folder**. Ten element spowoduje wygenerowanie danych wyjściowych jako pliku skompresowanego (zip). Jeśli dokument generowany przez element **Raport** jest umieszczany w wyjściowym pliku zip, jego zawartość zostanie skompresowana w celu zmniejszenia rozmiaru pliku wychodzącego.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Generowanie formatu ER w celu uzyskania skompresowanego dokumentu

1. Na stronie **Projektant formatów** wybierz opcję **Uruchom**.
2. Pobierz plik zip oferowany przez przeglądarkę sieci Web i otwórz go do przeglądu.
3. Zauważ, że rozmiar wygenerowanego dokumentu w formacie ZIP wynosi 1 KB.

    > [!NOTE] 
    > Stopień kompresji pliku XML, który jest przetrzymany przez ten plik zip, wynosi 87 procent. Współczynnik kompresji zależy od danych, które są kompresowane.

    ![Podgląd skompresowanego dokumentu wychodzącego](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Jeśli [miejsce docelowe](electronic-reporting-destinations.md) ER jest skonfigurowane dla elementu formatu, który generuje dane wyjściowe (element **Raport** w tym przykładzie), kompresja danych wyjściowych zostanie pominięta.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)

[Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)

[Odłóż wykonanie elementów XML w formatach raportowania elektronicznego](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]