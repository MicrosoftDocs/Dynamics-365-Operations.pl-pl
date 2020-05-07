---
title: Usunięte lub wycofane funkcje Platform
description: W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 04/17/2020
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
ms.openlocfilehash: f6365d42de5d19d960641f188cb6052ef07d721f
ms.sourcegitcommit: 6d6aa016c4971b0673d461b82fd80b060ae5f7a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/17/2020
ms.locfileid: "3268754"
---
# <a name="removed-or-deprecated-platform-features"></a>Usunięte lub wycofane funkcje Platform

[!include [banner](../includes/banner.md)]

W tym temacie opisano funkcje, które zostały usunięte lub są przeznaczone do usunięcia aktualizacji platformy z aplikacji Finance and Operations.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Ta lista ma na celu ułatwienie uwzględnienia usuniętych i przestarzałych funkcji we własnym planowaniu. 

> [!NOTE]
> Szczegółowe informacje o obiektów w rozwiązaniu aplikacjach Finance and Operations można znaleźć w temacie [Raporty dotyczące odwołań technicznych](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Można porównać różne wersje tych raportów, aby dowiedzieć się więcej o obiektach, które zostały zmienione lub usunięte w poszczególnych wersjach aplikacji Finance and Operations.

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Aktualizacje platformy dla wersji 10.0.11 aplikacji Finance and Operations

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

