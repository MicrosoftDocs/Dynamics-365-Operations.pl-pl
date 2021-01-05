---
title: Magazyn kopii zapasowej szablonów ER
description: W tym temacie objaśniono sposób korzystania z magazynu kopii zapasowej modułu raportowanie elektroniczne (ER) w celu odzyskania szablonów.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-13
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 136a81e661590d7af879e816c1142de85fb72e06
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681407"
---
# <a name="backup-storage-of-er-templates"></a>Magazyn kopii zapasowej szablonów ER

[!include [banner](../includes/banner.md)]

Użytkownicy biznesowi używają [Omówienie raportowania elektronicznego (ER)](general-electronic-reporting.md), który umożliwia użytkownikom biznesowym konfigurowanie formatów dokumentów wychodzących zgodnie z wymogami prawnymi obowiązującymi w różnych krajach i regionach. W skonfigurowanych formatach ER można używać wstępnie zdefiniowanych szablonów do generowania dokumentów wychodzących w różnych formatach, takich jak Microsoft Excel skoroszyty, Microsoft Word dokumenty i dokumenty PDF. W szablonach są wypełnione dane, których wymaga skonfigurowany przepływ danych dla generowanych dokumentów.

Każdy skonfigurowany format może zostać opublikowany jako część rozwiązania ER. Każde rozwiązanie ER można wyeksportować z jednego wystąpienia aplikacji Finance and Operations i zaimportować do innego wystąpienia.

Struktura ER używa funkcji [konfigurowania zarządzania dokumentami](../../fin-ops/organization-administration/configure-document-management.md) w celu zachowania wymaganych szablonów bieżącego wystąpienia aplikacji Finance and Operations. W zależności od ustawień struktury ER, można wybrać folder Microsoft Azure Magazyn obiektów BLOB lub folder Microsoft SharePoint jako fizyczną lokalizację magazynu podstawowego dla szablonów. (Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfigurowanie struktury raportowania elektronicznego (ER)](electronic-reporting-er-configure-parameters.md).) Tabela DocuValue zawiera pojedynczy rekord dla każdego szablonu. W każdym rekordzie pole **Informacje dotyczące dostępu** zawiera ścieżkę pliku szablonu, który znajduje się w skonfigurowanej lokalizacji magazynu.

Podczas zarządzania wystąpieniami aplikacji Finance and Operations można zdecydować, czy bieżące wystąpienie ma być migrowane do innej lokalizacji. Na przykład wystąpienie produkcji można migrować do nowego środowiska piaskownicy. Jeśli struktura ER jest skonfigurowana do przechowywania szablonów w magazynie obiektów BLOB, tabela DocuValue w nowym środowisku piaskownicy odwołuje się do wystąpienia magazynu obiektów BLOB w środowisku produkcyjnym. Jednak nie można uzyskać dostępu do tego wystąpienia ze środowiska piaskownicy, ponieważ proces migracji nie obsługuje migracji artefaktów w magazynie obiektów BLOB. Dlatego w przypadku próby uruchomienia formatu ER, który używa szablonu do generowania dokumentów biznesowych, wystąpi wyjątek i użytkownik jest powiadamiany o brakujący szablon. Użytkownik ma również możliwość użycia narzędzia do oczyszczania w celu usunięcia, a następnie ponownego zaimportowania konfiguracji formatu ER, która zawiera szablon. Ponieważ może być kilka konfiguracji formatu ER, ten proces może być czasochłonny.

Przechowywanie kopii zapasowych w module szablony ER ułatwia tworzenie szablonów w taki sposób, aby były one zawsze dostępne do generowania dokumentów biznesowych.

> [!NOTE]
> Tej funkcji można używać tylko wtedy, gdy w magazynie obiektów BLOB wybrano lokalizację magazynu fizycznego dla szablonów ER systemu.

## <a name="automated-recovery-and-notification"></a>Automatyczne odzyskiwanie i powiadamianie

W przypadku tej funkcji każdy szablon nowej konfiguracji formatu modułu ER w bieżącym środowisku jest automatycznie zapisywany w lokalizacji magazynu kopii zapasowej dla szablonów (tabela bazy danych ERDocuDatabaseStorage) po wystąpieniu następujących zdarzeń:

- Zaimportuje się nową konfigurację formatu ER, która zawiera szablon.
- Użytkownik wykona wersję roboczą konfiguracji formatu w formacie ER, która zawiera szablon.

Kopie zapasowe szablonów są migrowane do nowego wystąpienia aplikacji Finance and Operations jako część bazy danych aplikacji.

Jeśli do generowania dokumentów wychodzących jest wymagany szablon formatu ER, w celu przetwarzania płatności dostawców, takich jak generowanie raportów zawiadomienia o płatności i raporty kontrolne, na przykład nie można odnaleźć wymaganego szablonu w lokalizacji magazynu głównego, należy wykonać następujące czynności: zdarzenia:

- Jeśli szablon jest dostępny w lokalizacji magazynu kopii zapasowej, zostanie on automatycznie pobrany z lokalizacji magazynu kopii zapasowej, przywrócony do lokalizacji głównego magazynu i użyty w bieżącym wykonaniu.
- Każdy użytkownik przypisany do roli **dewelopera raportowania elektronicznego** lub **administratora systemu** jest powiadamiany o braku wydawanych szablonów za pośrednictwem centrum akcji. Wyświetlany komunikat zależy od wartości parametru **automatycznego uruchomienia procedury przywracania uszkodzonych szablonów w partii**:

    - Jeśli ten parametr jest **wyłączony**, komunikat zaleca uruchomienie procesu wsadowego w celu automatycznego rozwiązania podobnych problemów w odniesieniu do innych szablonów konfiguracji w formacie ER. Wiadomość zawiera łącze, które można wykorzystać do uruchomienia procesu wsadowego.
    - Jeśli ten parametr jest skonfigurowany jako **włączony**, komunikat powiadamia, że wykryto błąd brakujących szablonów i że nowy proces przetwarzania wsadowego, **przywrócenie przerwanych szablonów z wewnętrznej kopii zapasowej bazy danych** został automatycznie zaplanowane. Ten proces wsadowy spowoduje automatyczne rozwiązanie podobnych problemów dla innych szablonów.

Aby ustawić parametr **automatycznego uruchomienia procedury przywracania uszkodzonych szablonów w partii**, wykonaj kroki:

1. W aplikacji Finance and Operations otwórz stronę **Administracja organizacji \> Raportowanie elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.
3. W oknie dialogowym **parametry użytkownika** określ wymaganą wartość parametru **automatycznego uruchamiania procedury przywracania uszkodzonych szablonów w partii**.

> [!NOTE]
> Ten parametr jest definiowany jako użytkownik aplikacji i jest rejestrowana właściwa firma.

![Strona konfiguracji raportowania elektronicznego](./media/GER-BackupTemplates-1.png)

Na poniższej ilustracji pokazano przykład komunikatu wyświetlanego po **automatycznym uruchomieniu procedury przywracania uszkodzonych szablonów w parametrze wsadowym** jest ustawiony jako **włączony**.

![Strona arkusza płatności dostawcy](./media/GER-BackupTemplates-2.png)

Na poniższej ilustracji przedstawiono proces wsadowy **Przywracanie zepsutych szablonów z wewnętrznej kopii zapasowej bazy danych** na stronie **zadanie wsadowe**.

![Strona zadania wsadowe](./media/GER-BackupTemplates-3.png)

Dziennik wykonania zakończonego procesu wsadowego **Przywracanie zepsutych szablonów z wewnętrznej kopii zapasowej bazy danych** zawiera informacje o szablonach przywróconych z lokalizacji magazynu kopii zapasowej w lokalizacji magazynu głównego.

![Strona historii zadań wsadowych](./media/GER-BackupTemplates-4.png)

Domyślnie jest włączany proces automatycznego tworzenia kopii zapasowych szablonów znajdujących się w konfiguracjach formatu ER. Aby zatrzymać tworzenie kopii zapasowych szablonów, należy skonfigurować opcję **Zatrzymaj tworzenie kopii zapasowych szablonu** na **tak** na karcie **Załączniki** na stronie **Parametry elektronicznego reportowania**. Tę stronę można otworzyć z obszaru roboczego **Raportowanie elektroniczne**.

Jeśli dla opcji **Zatrzymaj tworzenie kopii zapasowych szablonów** ustawiono wartość **tak** i nie chcesz przechowywać kopii zapasowych poprzednio utworzonych szablonów, wybierz opcję **Oczyść magazyn kopii zapasowych** na stronie **Parametry raportowania elektronicznego**.

Jeśli środowisko zostało uaktualnione do aplikacji Finance and Operations w wersji 10.0.5 (październik 2019 r.), a użytkownik chce przeprowadzić migrację do nowego środowiska zawierającego konfiguracje formatu ER, które można uruchomić, należy wybrać opcję **Wypełnij w magazynie kopii zapasowych** na stronie **Parametry raportowania elektronicznego** przed migracją. Kliknięcie tego przycisku powoduje uruchomienie procesu tworzenia kopii zapasowych wszystkich dostępnych szablonów, dzięki czemu można je przechowywać w lokalizacji magazynu kopii zapasowych ER dla szablonów.

![Strona parametrów raportowania elektronicznego](./media/GER-BackupTemplates-5.png)

## <a name="manual-recovery"></a>Odzyskiwanie ręczne

Przejdź do pozycji **Administrowanie organizacją** \> **Raportowanie elektroniczne** \> **Przywróć uszkodzone szablony**, aby ręcznie zainicjować proces przywracania szablonów ER z lokalizacji magazynu kopii zapasowych do lokalizacji magazynu głównego. Przed uruchomieniem tego procesu na stronie **przywracania uszkodzonych szablonów** można określić, czy będzie on wykonywany interaktywnie, czy też zostanie zaplanowane odpowiednie przetwarzanie wsadowe.

## <a name="supported-deployments"></a>Obsługiwane wdrożenia

W aplikacji Finance and Operations w wersji 10.0.5 funkcja magazynowania kopii zapasowych szablonów ER jest dostępna tylko we wdrożeniach w chmurze.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania elektronicznego (RE)](general-electronic-reporting.md)

[Konfigurowanie struktury modułu Raportowanie elektroniczne (ER)](electronic-reporting-er-configure-parameters.md)
