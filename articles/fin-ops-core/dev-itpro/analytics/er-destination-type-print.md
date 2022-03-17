---
title: Typ miejsca docelowego drukarka
description: Ten temat zawiera wyjaśnienia dotyczące możliwości skonfigurowania miejsca docelowego drukarki dla każdego składnika typu FOLDER lub PLIK w formacie raportowania elektronicznego (ER).
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388295"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Miejsce docelowe — drukarka

[!include [banner](../includes/banner.md)]

Wygenerowany dokument można wysłać bezpośrednio do drukarki sieciowej w celu bezpośredniego drukowania.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować agenta rozsyłania dokumentów, a następnie zarejestrować drukarki sieciowe. W celu zdobycia większezj ilości informacji, zobacz [Instalowanie Agenta rozsyłania dokumentów w celu obsługi druku przez sieć](./install-document-routing-agent.md).

## <a name="make-the-printer-destination-available"></a>Umożliwia udostępnienie drukarki jako miejsca docelowego

Aby udostępnić **drukarkę** jako miejsce docelowe w bieżącej instancji rozwiązania Microsoft Dynamics 365 Finance, przejdź do obszaru roboczego **zarządzanie funkcją** i włącz funkcje w następującej kolejności:

1. Konwertuj dokumenty wychodzące raportowania elektronicznego z formatów Microsoft Office na PDF
2. Agent rozsyłania dokumentów jako cel raportowania elektronicznego dla dokumentów wychodzących

[![Włączanie funkcji lokalizacji docelowej drukarka ER w module Zarządzanie funkcjami.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Możliwość stosowania

#### <a name="pdf-printing"></a>Drukowanie kodu przyczyny rejestracji

W wersjach Finance wcześniejszych niż 10.0.18 miejsce docelowe **Drukarka** może być skonfigurowane tylko dla składników plików, które są używane do generowania danych wyjściowych w formacie PDF do wydrukowania (**PDF Merger** lub **PDF file** elementy formatu) lub format Microsoft Office Excel i Word (**plik Excel** element formatu). Jeśli dane wyjściowe są generowane w formacie PDF, są one wysyłane do drukarki. Gdy dane wyjściowe są generowane w formacie Office przy użyciu elementu formatu **plik Excel**, są one automatycznie konwertowane do formatu PDF, a następnie wysyłane do drukarki.

Jednak w wersji 10.0.18 można skonfigurować **drukarkę** docelową dla elementu formatu **pliku Wspólne**. Ten element formatu jest głównie używany do generowania danych wyjściowych w formacie TXT lub XML. Możesz skonfigurować format ER, który zawiera element formatu **Wspólny plik** jako główny element formatu i element formatu **Zawartość binarna** jako jedyny zagnieżdżony element w nim. W takim przypadku element **wspólny plik** format będzie tworzyć dane wyjściowe w formacie określonym w powiązaniu skonfigurowanym dla elementu **formatu zawartości binarnej**. Na przykład możesz skonfigurować to powiązanie, aby [wypełnić](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) ten element treścią załącznika [Zarządzanie dokumentami](../../fin-ops/organization-administration/configure-document-management.md) w formacie PDF lub Office (Excel lub Word). Dane wyjściowe można wydrukować za pomocą skonfigurowanego miejsca docelowego **drukarki**. 

> [!NOTE]
> Po wybraniu elementu formatu **Wspólny\\Plik** w celu skonfigurowania lokalizacji docelowej **Drukarka**, nie ma możliwości zagwarantowania w czasie projektowania, że wybrany element wygeneruje dane wyjściowe w formacie PDF lub dane wyjściowe, które można przekonwertować do formatu PDF. W związku z tym zostanie wyświetlony następujący komunikat ostrzegawczy: „Upewnij się, że dane wyjściowe wygenerowane przez wybrany składnik formatu mogą być konwertowane na pliki PDF. W przeciwnym razie usuń zaznaczenie opcji „Konwertuj na plik PDF” Należy podjąć odpowiednie kroki, aby zapobiec problemom w czasie wykonywania, gdy dane wyjściowe nie w formacie PDF lub innym niż PDF są udostępniane do drukowania w czasie wykonywania. Jeśli spodziewasz się otrzymać dane wyjściowe w formacie Office (Excel lub Word), musisz wybrać opcję **Konwertuj na PDF**.
>
> W wersji 10.0.26 i nowszych, aby użyć opcji **Konwertuj na PDF**, musisz wybrać **PDF** dla parametru **Typ routingu dokumentów** skonfigurowanej **Drukarki** Miejsce docelowe.

#### <a name="zpl-printing"></a>Drukowanie kodu przyczyny rejestracji

W wersji 10.0.26 i nowszych możesz skonfigurować lokalizację docelową **Drukarka** dla elementu formatu **Wspólny\\Plik**, wybierając **ZPL** dla **Typ routingu dokumentów** parametr. W takim przypadku opcja **Konwertuj na plik PDF** jest ignorowana w czasie wykonywania, a dane wyjściowe TXT lub XML są wysyłane bezpośrednio do wybranej drukarki przy użyciu umowy Zebra Programming Language (ZPL) [agenta rozsyłania dokumentów (TXT)](install-document-routing-agent.md). Ta funkcja jest dostępna w przypadku formatu ER reprezentującego układ etykiet ZPL II w celu drukowania różnych etykiet.

[![Ustawianie parametru Typ rozsyłania dokumentów w oknie dialogowym Ustawienia docelowe.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Aby uzyskać więcej informacji o tej funkcji, zobacz [projektowanie nowego rozwiązania ER w celu drukowania etykiet ZPL](er-design-zpl-labels.md).

### <a name="limitations"></a>Ograniczenia

Lokalizacja docelowa **Drukarka** jest zaimplementowana tylko dla wdrożeń w chmurze.

### <a name="use-the-printer-destination"></a>Użyj miejsca docelowego drukarka

1. Ustawienie opcji **włączone** na wartość **Tak** powoduje wysłanie wygenerowanego dokumentu do drukarki.
2. W polu **Nazwa drukarki** wybierz żądaną drukarkę sieciową.
3. Ustawienie parametrt **Zapisywanie w archiwum drukowania?** na wartość **Tak** spowoduje przechowywanie wygenerowanych danych wyjściowych w archiwum drukowania, tak aby było dostępne do dalszego drukowania. Aby później uzyskać dostęp do zarchiwizowanych danych wyjściowych **Zarządzanie organizacją** \> **Raporty i zapytania** \> **Archiwum raportów**.

[![Używanie miejsca docelowego drukarka.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> Opcja **Konwertuj na plik PDF** nie musi być włączona podczas konfigurowania miejsca docelowego **Drukarka**. Konwersja plików PDF na potrzeby drukowania nastąpi nawet wtedy, gdy opcja jest wyłączona.

Aby podczas drukowania dokumentu wychodzącego w formacie programu Excel używana była określona [orientacja strony](electronic-reporting-destinations.md#SelectPdfPageOrientation), należy włączyć opcję **Konwertuj na PDF**. Ustawienie opcji **Konwertuj na PDF** na wartość **Tak** powoduje, że staje się dostępne pole **Orientacja strony**. W polu **Orientacja strony** możesz wybrać orientację strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md)
- [Miejsca docelowe raportowania elektronicznego (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
