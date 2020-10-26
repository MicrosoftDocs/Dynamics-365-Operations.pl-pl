---
title: Usunięte lub wycofane funkcje Platform
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 09/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 51d1d0ed2ce95573ec123121999d73446a7e4ea4
ms.sourcegitcommit: 6e0d6d291d4881b16a677373f712a235e129b632
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/08/2020
ms.locfileid: "3971452"
---
# <a name="removed-or-deprecated-platform-features"></a>Usunięte lub wycofane funkcje Platform

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.15 aplikacji Finance and Operations

> [!NOTE]
> Wersja 10.0.15 to wersja zapoznawcza. Zawartość i funkcje mogą ulec zmianie. Aby uzyskać więcej informacji dotyczących wydań wersji zapoznawczych, zobacz [Aktualizacje do jednej wersji usługi — często zadawane pytania](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Dodatek Visual Studio do stosowania poprawek metadanych

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Poprawki metadanych nie są już obsługiwane w aktualizacjach usługi [One Version](../../fin-ops/get-started/one-version.md), która zostały wprowadzone w lipcu 2018 r. w wersji 8.1. |
| **Zamieniona przez inną funkcję?**   | Poszczególne poprawki metadanych nie są dostępne dla obsługiwanych wersji. Zamiast tego stosowane są skumulowane aktualizacje jakości. |
| **Powiązane obszary produktów**         | Dodatki Visual Studio |
| **Opcja wdrażania**              | Maszyny wirtualne programowania |
| **Stan**                         | W wersji 10.0.15 dodatek nie jest już uwzględniany w narzędziach Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.14 aplikacji Finance and Operations

> [!NOTE]
> Wersja 10.0.14 to wersja zapoznawcza. Zawartość i funkcje mogą ulec zmianie. Aby uzyskać więcej informacji dotyczących wydań wersji zapoznawczych, zobacz [Dostępność aktualizacji usługi](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/public-preview-releases).


### <a name="online-users-page"></a>Strona Zalogowani użytkownicy 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | To jest starsza strona, która została stworzona dla poprzedniej architektury klient / serwer. Informacje na tej stronie nie zawsze są dokładne, co może być mylące i wprowadzające w błąd. |
| **Zamieniona przez inną funkcję?**   | W przyszłej aktualizacji zostanie wyświetlona nowa strona.|
| **Powiązane obszary produktów**         | Administrowanie systemem |
| **Opcja wdrażania**              | Wszyscy |
| **Stan**                         | Do października 2021 ten formularz zostanie usunięty.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.13 aplikacji Finance and Operations


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Kod niestandardowy zdefiniowany we właściwościach raportu SSRS 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Ogólnie rzecz, kod niestandardowy oferuje ograniczone korzyści jednocześnie, wymaga znaczącego odzyskania i obliczenia do działu pomocy technicznej. Kod niestandardowy jest używany głównie przez autorów raportów do wywoływania metod publicznych z zestawu kodu niestandardowego. Jednak usługa hostowana w chmurze nie obsługuje odwołań do niestandardowych zestawów raportów SSRS. |
| **Zamieniona przez inną funkcję?**   | Autorzy raportów mogą kontynuować odwołując się do interfejsów API publicznego rozwiązania .NET dla operacji matematycznych, konwersji i formatowania z dowolnego wyrażenia pola tekstowego. Aby uzyskać więcej informacji, zobacz [Dodaj kod do raportu (SSRS)](https://docs.microsoft.comsql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Powiązane obszary produktów**         | Podzbiór projektów raportów aplikacji zdefiniowany w module RDL, które zawierają kod niestandardowy. |
| **Opcja wdrażania**              | Wszystko |
| **Stan**                         | W przypadku wersji 10.0.13 kompilator rozpocznie generowanie ostrzeżenia o wystąpieniach, w których w definicji raportu SSRS zostanie wykryty kod niestandardowy. Aby rozwiązać ten problem, Otwórz definicję projektu raportu i Usuń wszystkie artefakty kodu niestandardowego. Ostrzeżenie kompilatora zostanie zastąpione błędem kompilatora w przyszłej aktualizacji.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Uaktualnienie trzech bibliotek składników jQuery 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Są aktualizowane trzy biblioteki składników jQuery dla poprawek zabezpieczeń oraz do obsługi waluty.   
| **Zamieniona przez inną funkcję?**   | Dotyczy to następujących bibliotek: jQuery (do wersji 3.5.0 z wersji 2.1.4), interfejsu użytkownika jQuery (do wersji 1.12.1 z wersji 1.11.4), jQuery qTip (do wersji 3.0.3 z 2.2.1). Wskazówki dotyczące migracji zostały dostarczone w trybie online przez jQuery.  |
| **Powiązane obszary produktów**         | Rozszerzalne kontrolki, w szczególności niestandardowy kod JavaScript wykorzystujący przestarzałe lub usunięte interfejsy API |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W przypadku wersji 10.0.13/aktualizacji platformy 37 klienci mogą opcjonalnie przełączać się do najnowszych bibliotek, włączając funkcję „Uaktualnij trzy biblioteki składników jQuery”. Przechodzenie do nowych bibliotek będzie obowiązkowe wraz z wydaniem z kwietnia 2021, aby umożliwić migrację interfejsów API, których dotyczy problem.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Istniejący interfejs API kontroli/forceLegacyGrid() sieci

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Istniejąca kontrolka siatki jest zastępowany nową kontrolką siatki. |
| **Zamieniona przez inną funkcję?**   | [Nowa kontrolka siatki](../..//fin-ops/get-started/grid-capabilities.md) |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W wersji 10.0.13 nowa kontrola sieci jest ogólnie dostępna, a klienci mogą opcjonalnie włączyć tę funkcję. Nowa kontrola sieci stanie się obowiązkowa w wersji z października 2021 r. Gdy nowa kontrola sieci stanie się obowiązkowa, API **forceLegacyGrid()** nie będzie już honorowane. |

### <a name="personalization-without-saved-views"></a>Personalizacja bez zapisanych widoków 

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Podsystem personalizacji został zastąpiony funkcją zapisane widoki, dzięki czemu ma lepszą wydajność i oferuje dodatkowe możliwości. |
| **Zamieniona przez inną funkcję?**   | Zapisane widoki |
| **Powiązane obszary produktów**         | Klient sieci Web |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | W wersji 10.0.13/platform aktualizację 37, funkcja zapisanych widoków jest ogólnie dostępna, a odbiorcy mogą opcjonalnie włączyć tę funkcję. Funkcja zapisanych widoków stanie się obowiązkowa w wersji z października 2021 r. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.12 aplikacji Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Rozszerzenia formularza siatki lub grup kontrolek zawierające nieprawidłowe odwołania do pól

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Właściwość Grupa danych w kontrolkach siatki i grup służy do automatycznego pokazywania wszystkich pól grupy pól. Kontrolka siatki lub grupy dodana przez rozszerzenie może zawierać pola, które nie są już zdefiniowane w grupie pól, lub może nie mieć pól, które są zdefiniowane w grupie pól. Może to spowodować niespójne działanie w czasie wykonywania. Aktualizacje platformy dla wersji 10.0.12 aplikacji Finance and Operations teraz klasyfikuje ten problem jako *ostrzeżenie* kompilatora. Aby rozwiązać ten problem, otwórz rozszerzenie formularza i zapisz je.
| **Zamieniona przez inną funkcję?**   | To ostrzeżenie kompilatora zostanie zastąpione błędem kompilatora w przyszłej aktualizacji. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Ostrzeżenie kompilatora jest wprowadzone w aktualizacjach platformy dla wersji 10.0.12 aplikacji Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.11 aplikacji Finance and Operations

### <a name="explicit-safe-lists-for-self-service-environments"></a>Jawne bezpieczne listy dla środowisk samoobsługowych

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Proces przenoszenia adresu IP do list bezpiecznych został zmieniony. Samoobsługa nie obsługuje już bezpiecznych list adresów IP. |
| **Zamieniona przez inną funkcję?**   | Aby uzyskać więcej informacji, zobacz [Konfiguracja warunkowego dostępu do Azure Active Directory](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Powiązane obszary produktów**         | Zabezpieczenia |
| **Opcja wdrażania**              | W chmurze |
| **Stan**                         | **Przestarzałe:** Ta funkcja jest całkowicie przestarzała w przypadku wdrożeń samoobsługowych. |

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Aby można było obsługiwać najnowsze wersje Visual Studio, niektóre zmiany należy wprowadzać w odniesieniu do rozszerzeń X++ dla Visual Studio. Te zmiany są niezgodne z Visual Studio 2015. |
| **Zamieniona przez inną funkcję?**   | Visual Studio 2017 zamieni Visual Studio 2015 jako wdrożoną i wymaganą wersję. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Po zaanonsowaniu dostępności nowych maszyn wirtualnych (VMs) z Visual Studio 2017, istniejące maszyny wirtualne mające tylko Visual Studio 2015 będą trzeba ponownie wdrożyć przed 1 wydaniem w 2021 roku. |

### <a name="field-groups-containing-invalid-field-references"></a>Grupy pól zawierających nieprawidłowe pole odwołania

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Grupy pól w definicjach metadanych tabeli mogą zawierać nieprawidłowe odwołania pól. Jeśli te grupy pól zostaną wdrożone, mogą powodować awarie środowiska wykonawczego w Financial Reporting i Microsoft SQL Server Reporting Services (SSRS). Aktualizacja platformy 23 wprowadziła *ostrzeżenie* kompilatora, które umożliwiło zaadresowanie tego problemu z metadanymi. Aktualizacje platformy dla wersji 10.0.11 aplikacji Finance and Operations klasyfikują ten problem jako *błąd* kompilatora.<p>Aby naprawić ten problem, należy wykonać następujące czynności.</p><ol><li>Usuń nieprawidłowe odwołanie pola z definicji grupy pól tabel.</li><li>Kompiluj ponownie.</li><li>Upewnij się, że wszystkie błędy zostały rozwiązane.</li></ol> |
| **Zamieniona przez inną funkcję?**   | Ten błąd kompilatora powoduje trwałe zastąpienie ostrzeżenia kompilatora.  |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | **Przestarzałe:** Ostrzeżenie kompilatora jest błędem kompilatora w aktualizacjach platformy dla wersji 10.0.11 aplikacji Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licencje ISV utworzone przy użyciu algorytmu wyznaczania wartości skrótu SHA1

|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Proces tworzenia licencji niezależnych dostawców oprogramowania (ISV) został zmieniony. Aby uzyskać więcej informacji, zajrzyj do [Licencjonowanie niezależnego dostawcy oprogramowania (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Zamieniona przez inną funkcję?**   | Tak. Do tworzenia licencji używaj Windows PowerShell. |
| **Powiązane obszary produktów**         | Narzędzia programistyczne Visual Studio. |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | <strong>Przestarzałe:</strong> licencje ISV utworzone za pomocą algorytmu wyznaczania wartości skrótu SHA1. Ten algorytm jest zależny od certyfikatów utworzonych za pomocą narzędzia MakeCert, a to narzędzie jest przestarzałe.<p><strong>Przestarzałe:</strong> użycie algorytmu SHA1 na potrzeby zabezpieczeń lub wyznaczania wartości skrótu. Algorytm SHA1 przestanie działać na początku 2021. Dlatego nie należy go już używać.<p><strong>Usunięto</strong> : Obsługa żądań przychodzących lub wychodzących dotyczących zabezpieczeń TLS (Transport Layer Security) 1.0 i TLS 1.1. |

## <a name="platform-update-32"></a>Aktualizacja platformy Update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Okno dialogowe zmiana żądania przepływu pracy nie zawiera już listy rozwijanej wyboru użytkownika
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Była to kwestia błędu zabezpieczeń, ponieważ żądanie zmiany może zostać wysłane do niezamierzonego użytkownika. Był to również błąd użyteczności, ponieważ zmuszał użytkownika do określenia, kto był wytwórcą przepływu pracy został i ręczny jego wybór.  |
| **Zamieniona przez inną funkcję?**   | Nie |
| **Powiązane obszary produktów**         | Przepływ pracy |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Lista rozwijana wyboru użytkownika została usunięta z okna dialogowego zmiany żądania w aktualizacji platformy 32. Żądania zmiany żądania zostaną automatycznie wysłane do inicjatora zgodnie z zamierzeniem. Aby uzyskać więcej informacji o tych funkcjach, zapoznaj się z tematem [Akcje w procesach zatwierdzania w przepływie pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Osadzone łącza drążenia wskroś nie są już obsługiwane w dokumentach z podziałem, renderowanych przez usługę hostowaną w chmurze 
|   |  |
|------------|--------------------|
| **Przyczyna wycofania/usunięcia** | Adresy URL nawigacji osadzone w dokumentach renderowanych przez usługę mogą zawierać poufne dane biznesowe. Usuwamy pomoc techniczną dla łączy typu „drążenie wskroś” w dokumentach jako środek bezpieczeństwa, aby dodatkowo chronić dane odbiorców. Użytkownicy będą również mogli uzyskać lepszą wydajność podczas interaktywnego tworzenia dokumentów w wyniku tej zmiany.  |
| **Zamieniona przez inną funkcję?**   | Nr |
| **Powiązane obszary produktów**         | Raportowania |
| **Opcja wdrażania**              | Wszystkich |
| **Stan**                         | Ta funkcja jest aktywnie usuwana z usługi.<br><br>Nowoczesne oprogramowanie klienckie oferuje wiele opcji tworzenia widoków, które zawierają automatycznie generowane łącza umożliwiające nawigację po aplikacji. Dokumenty z podziałem, renderowane przez usługę, są zalecane w przypadku komunikacji zewnętrznej, które są wysyłane, archiwizowane i drukowane dla odbiorców. Ulepszono możliwości wyświetlania podglądu dokumentów bezpośrednio w przeglądarce, która oferuje bezpośredni dostęp do drukarek lokalnych. Aby uzyskać więcej informacji, zobacz [Podgląd dokumentów PDF za pomocą osadzonej przeglądarki](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Poprzednie oświadczenia o usuniętych lub wycofanych funkcjach
Aby dowiedzieć się więcej o funkcjach, które zostały usunięte lub wycofane w poprzednich wersjach, zobacz temat [Usunięte lub wycofane funkcje w poprzednich wersjach](../migration-upgrade/deprecated-features.md).

