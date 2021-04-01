---
title: Instalowanie, konfigurowanie i aktualizowanie portalu klienta
description: W tym temacie przedstawiono szczegółowe informacje na temat licencjonowania i instrukcje konfiguracji dla portalu klienta.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: fa95995320a0f81c040eeebe6fd796200fbff13f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255044"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Instalowanie, konfigurowanie i aktualizowanie portalu klienta

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Wymagania dotyczące licencji

Aby zaimplementować Portal odbiorców, należy dysponować następującymi licencjami:

- **Portale Power Apps** — Ta licencja jest wymagana do obsługi portalu klienta. Portale są licencjonowane na podstawie użycia. Aby uzyskać więcej informacji, zajrzyj do [wymagań licencyjnych dotyczących portali Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Podwójny zapis** — wymagane są licencje niezbędne do włączenia podwójnego zapisywania dla tabel Supply Chain Management. Aby uzyskać więcej informacji, zobacz [Wymagania systemowe dotyczące podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Zależności od podwójnego zapisu i portali Power Apps

Portal klienta zależy od portali Power Apps i podwójnego zapisu, co pokazano na poniższej ilustracji.

![Zależności portalu klienta](media/customer-portal-elements.png "Zależności portalu klienta")

W przeciwieństwie do innych funkcji Supply Chain Management, szablon Portalu klienta znajduje się w portalach Power Apps. Z tego względu Portal klienta jest ograniczony przez funkcje i możliwości dostarczane przez portale Power Apps i tabele z podwójnym zapisem.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Konfiguracja wymagana do włączenia portalu klienta

Po upewnieniu się, że użytkownik dysponuje wymaganymi licencjami, można skonfigurować podwójny zapis w sposób opisany w [instrukcjach wstępnej synchronizacji podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).

Należy pamiętać, aby w podwójnym zapisywaniu włączyć następujące mapowania tabel:

- Nagłówek zamówienia sprzedaży
- Szczegóły zamówienia sprzedaży
- Konta
- Kontakty
- Produkty

Po zakończeniu tych ustawień można zastrzec szablon Portal klienta.

## <a name="provision-the-customer-portal"></a>Ustanowienie portalu klienta

Przed rozpoczęciem należy upewnić się, że wykonano już [wymagane ustawienia](#required-setup). Następnie należy wykonać poniższe kroki w celu zainicjowania obsługi portalu klienta.

1. Przejdź do [make.powerapps.com](https://make.powerapps.com/).
2. Upewnij się, że korzystasz z środowiska, w którym jest włączony podwójny zapis.
3. Na karcie **Tworzenie** przewiń w dół do sekcji **Rozpocznij od szablonu**, a następnie wybierz szablon o nazwie **Portal klienta**.
4. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie.

Po zakończeniu obsługi administracyjnej można uzyskać dostęp do portalu klienta w sekcji **Twoje aplikacje** na stronie **Głównej**.

> [!NOTE]
> Jeśli rozwiązanie podwójnego zapisywania nie jest zainstalowane w środowisku, w którym pracujesz, zostanie wyświetlony komunikat o błędzie, a Portal klienta nie zostanie zainicjowany.

## <a name="update-the-customer-portal"></a>Aktualizacja portalu klienta

Do portalu klienta można później dodać więcej funkcji. Wszelkie zmiany, które firma Microsoft wprowadza w podstawowych składnikach rozwiązania, będą automatycznie widoczne w danym środowisku. Jednak witryna sieci Web, która jest zainicjowana w środowisku, nie będzie automatycznie uwzględniać zmian wprowadzonych w danych konfiguracyjnych. Należy ręcznie zastosować te zmiany, pobierając kod z nowego szablonu i scalając go z zainicjowaną witryną sieci Web.

## <a name="additional-resources"></a>Dodatkowe zasoby

Aby dowiedzieć się, jak można skonfigurować i dostosować Portal klienta, należy zacząć od przejrzenia następującej dokumentacji dla podstawowych technologii:

- [Dokumentacja portali Power Apps](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Dokumentacja podwójnego zapisu](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Aby efektywnie zarządzać portalami, należy zrozumieć portale Power Apps i cykl życia Microsoft Dataverse. Aby uzyskać więcej informacji, zobacz następujące zasoby:

- [Cykl życia portalu — informacje](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Uaktualnianie portalu](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migruj konfigurację portalu](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Zarządzanie cyklem życia rozwiązania: Dynamics 365 dla aplikacji Customer Engagement](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]