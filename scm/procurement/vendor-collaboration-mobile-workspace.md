---
title: "Mobilny obszar roboczy Współpraca z dostawcami dla aplikacji Microsoft Dynamics 365 for Operations"
description: "Dzięki mobilnemu obszarowi współpracy z dostawcami dostawcy mogą być na bieżąco z zamówieniami zakupu, które im wysłano do zatwierdzenia, oraz wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267074
ms.assetid: 1d293b3a-2fa2-418d-9347-78c2809d67fe
ms.search.region: global
ms.author: mkirknel
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d5157e6f4b10b6158aa08279a9f68dae676f5666
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-collaboration-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobilny obszar roboczy Współpraca z dostawcami dla aplikacji Microsoft Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Dzięki mobilnemu obszarowi współpracy z dostawcami dostawcy mogą być na bieżąco z zamówieniami zakupu, które im wysłano do zatwierdzenia, oraz wyświetlać informacje o nowych i zaktualizowanych zamówieniach zakupu i osobach kontaktowych.

<a name="prerequisites"></a>Wymagania wstępne
-------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Przeczytaj na temat platformy mobilnej Microsoft Dynamics 365 for Operations</td>
<td><a href="https://ax.help.dynamics.com/en/wiki/mobile-development-handbook/">Platforma komórkowa Dynamics 365 for Operations</a></td>
</tr>
<tr class="even">
<td>Dynamics 365 for Operations</td>
<td>Upewnij się, że używasz środowiska, w którym zainstalowano program Microsoft Dynamics 365 for Operations w wersji 1611 oraz aktualizację nr 3 platformy Microsoft Dynamics 365 for Operations (z listopada 2016 r.).</td>
</tr>
<tr class="odd">
<td><span style="color: #000000">Urządzenie przenośne, które ma zainstalowaną aplikację Dynamics 365 for Operations</span></td>
<td><span style="color: #000000">Pobierz aplikację Dynamics 365 for Operations ze sklepu z aplikacjami dla urządzeń komórkowych.</span></td>
</tr>
<tr class="even">
<td>Poprawka KB 4013633</td>
<td>Zainstaluj poprawkę, która włączy obsługę obszarów roboczych zawartych w usłudze Dynamics 365 for Operations.</td>
</tr>
<tr class="odd">
<td><span style="color: #ff0000"><span style="color: #000000">Poprawka KB 3216943</span> </span></td>
<td>Zainstaluj poprawkę, aby włączyć obsługę mobilnego obszaru roboczego współpracy z dostawcami.</td>
</tr>
<tr class="even">
<td>Użytkownik u dostawcy musi mieć dostęp do internetowego interfejsu współpracy z dostawcami w usłudze Dynamics 365 for Operations i skonfigurować użytkownika zarządzającego współpracą z dostawcą.</td>
<td>Wykonaj kroki opisane w poniższych tematach, aby skonfigurować internetowy interfejs współpracy dostawcy i w nim pracować.
<ul>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-external-vendors/">Używanie obszaru roboczego współpracy z dostawcami do pracy z zewnętrznymi dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/manage-vendor-collaboration-users/">Zarządzanie użytkownikami portalu współpracy z dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/set-up-and-maintain-vendor-collaboration/">Konfigurowanie i obsługa współpracy z dostawcami</a></li>
<li><a href="https://ax.help.dynamics.com/en/wiki/using-vendor-collaboration-to-work-with-customers-in-dynamics-365-for-operations/">Używanie obszaru roboczego współpracy z dostawcami do pracy z odbiorcami w programie Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="overview"></a>Przegląd
Mobilny obszar roboczy Współpraca z dostawcami przekazuje dostawcom na bieżąco informacje o nowych zamówieniach zakupu, dzięki czemu widzą oni zamówienia zakupu i mogą na nie reagować w kliencie internetowym usługi Dynamics 365 for Operations. 

**Uwaga:** Mobilny obszar roboczy powinien być używany jako dodatek do internetowego interfejsu współpracy z dostawcami, a nie zamiast niego. 

W mobilnym obszarze roboczym współpracy z dostawcami dostawcy widzą nowe zamówienia zakupu wysyłane do zatwierdzenia. Obszar pokazuje różne informacje z zamówień zakupu, takie jak produkty, ilości i żądane daty dostawy. W zależności od konfiguracji konkretnego dostawcy są dostępne wybrane informacje o cenach. 

Gdy użytkownik zaloguje się jako dostawca, będzie widział, na które zamówienia zakupu odpowiedziano, a które zamówienia zakupu wciąż oczekują na działania odbiorcy. Być może dostawca zaproponował inną datę dostawy, która nie jest jeszcze uzgodniona z klientem, w związku z czym zamówienie zakupu oczekuje na działanie klienta. Dostawca będzie także widział listę zamówień zakupu, które są potwierdzone, ale nie zostały jeszcze dostarczone. 

Aby odpowiedzieć na zamówienie zakupu, dostawca musi użyć internetowego interfejsu współpracy z dostawcami, który jest dostępny w kliencie internetowym usługi Dynamics 365 for Operations. Również w tym miejscu dostawca uzyska więcej informacji o zamówieniu, takich jak załączone dokumenty, adresy dostawy dla poszczególnych wierszy oraz opłaty, które musi ponieść. 

Posiadając specjalną rolę zabezpieczeń, dostawca może zobaczyć osoby kontaktowe zarejestrowane na jego koncie dostawcy. Ta sama rola zabezpieczeń pozwala wyświetlić stan każdego przesłanego wniosku użytkownika. 

Tworzenie nowych osób kontaktowych i przesyłanie nowych wniosków użytkowników musi się odbywać się w interfejsie współpracy z dostawcami dostępnym w kliencie internetowym usługi Dynamics 365 for Operations. 

W mobilnym obszarze roboczym dostawca może wykonywać następujące czynności:

-   Wyświetlanie nowych zamówień zakupu wysłanych dostawcy.
-   Wyświetlanie zamówień zakupu, na które dostawca odpowiedział i które oczekują działania ze strony odbiorcy.
-   Wyświetlanie zamówień zakupu, które są w stanie potwierdzenia, ale nie zostały jeszcze w pełni przyjęte.
-   Wyświetlanie informacji o osobach kontaktowych zarejestrowanych na koncie dostawcy (wymaga dodatkowej roli zabezpieczeń).
-   Wyświetlanie informacji o stanie realizacji wniosku użytkownika wysłanego przez dostawcę (wymaga dodatkowej roli zabezpieczeń).

## <a name="get-started"></a>Rozpocznij
Aby rozpocząć pracę na urządzeniu przenośnym:

1.  W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Microsoft Dynamics 365 for Operations.
2.  Uruchom aplikację na urządzeniu.
3.  Wprowadź adres URL usługi Dynamics 365.
4.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Microsoft Dynamics 365 for Operations.

Po zalogowaniu do aplikacji nie zobaczysz żadnego obszaru roboczego. Aby widzieć obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary w aplikacji Dynamics 365 for Operations. Aby opublikować obszar roboczy, potrzebujesz uprawnienia administracyjnych systemu.

1.  Uruchom program Dynamics 365 for Operations.
2.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Parametry systemu**.
3.  Wybierz opcję **Zarządzaj aplikacją mobilną**.
4.  Wybierz obszar roboczy **Współpraca z dostawcami**, aby go opublikować na platformie mobilnej.
5.  Wybierz opcję **Opublikuj obszar roboczy**.
6.  Odśwież swoje urządzenie, a zobaczysz opublikowane obszary robocze.
7.  Zaznacz obszar roboczy **Współpraca z dostawcami**. Zobaczysz następującą stronę.

    [![vendor-collaboration-mobile-app](./media/vendor-collaboration-mobile-app.png)](./media/vendor-collaboration-mobile-app.png)

## <a name="contacts"></a>Kontakty
Na stronie **Kontakty** widać wszystkie osoby kontaktowe, które zostały skonfigurowane na koncie dostawcy. Pokazuje ona imię i nazwisko osoby kontaktowej, jej podstawowy adres e-mail oraz alias (jeśli istnieje). Wskazuje również, czy konto użytkownika osoby kontaktowej jest aktywne. Po zaznaczeniu osoby kontaktowej zobaczysz jej szczegóły, takie jak firmy, dla których ta osoba jest osobą kontaktową, oraz dane kontaktowe, takie jak numer telefonu lub różne adresy e-mail.

## <a name="user-requests"></a>Wnioski użytkownika
Na stronie **Wnioski użytkowników** są wyświetlane wszystkie wnioski użytkowników przesłane przez Ciebie za pośrednictwem internetowego interfejsu współpracy z dostawcami i możesz śledzić stan ich rozpatrywania. Po wybraniu wniosku użytkownika możesz zobaczyć, o co wnioskowano, dodać lub zdezaktywować użytkownika, zmienić zabezpieczenia oraz zobaczyć, o które role zabezpieczeń poproszono dla użytkownika.

## <a name="purchase-orders-ready-for-review"></a>Zamówienia zakupu gotowe do przejrzenia
Strona **Zamówienia zakupu gotowe do przejrzenia** pozwala zobaczyć wszystkie zamówienia zakupu wysłane przez odbiorcę, na które jeszcze nie udzielono odpowiedzi. Można wyświetlić wybrane informacje dotyczące zamówienia, na przykład o które produkty wnioskowano i kiedy należy je dostarczyć. Informacje o cenach są dostępne tylko wtedy, gdy dostawca skonfigurował tę opcję. Można zobaczyć, czy zamówienie zakupu ma notatki i załączniki. Aby otworzyć załączniki, należy użyć obszaru roboczego współpracy z dostawcami w kliencie internetowym. Wybierz opcję **Wiersz zamówienia zakupu**, aby wyświetlić wszystkie wiersze ze szczegółami. Należy zauważyć, że dla każdego wiersza wskaźnik pokaże, czy istnieją notatki lub załączniki albo czy adres dostawy jest inny od wyświetlanego w nagłówku. Aby odpowiedzieć na zamówienie zakupu, należy użyć klienta internetowego współpracy z dostawcami.

## <a name="awaiting-customer-action"></a>Oczekiwanie na akcję odbiorcy
Strona **Oczekiwanie na akcję odbiorcy** pozwala znaleźć zamówienia zakupu, na które Ty lub inna w Twojej firmie z dostępem do obszaru roboczego współpracy z dostawcami udzieliliście odpowiedzi. Zamówienia zakupu są widoczne na tej liście tylko wtedy, gdy odbiorca musi wykonać jedną z następujących czynności w zamówieniu zakupu:

-   Jeśli zamówienie zakupu zostało odrzucone, odbiorca musi zaktualizować wysłane zamówienie i wysłać je ponownie lub anulować zamówienie i wysłać nowe. Jeśli zamówienie zakupu zostanie wysłane ponownie, zniknie ze strony **Oczekiwanie na akcję odbiorcy**.
-   Jeśli zamówienie zakupu zostało zaakceptowane ze zmianami, odbiorca musi zaktualizować oryginalne zamówienie i wysłać je ponownie do przejrzenia albo zaktualizować zgodnie ze zmianami i natychmiast potwierdzić. W obu przypadkach zamówienie zakupu zniknie ze strony **Oczekiwanie na akcję odbiorcy**.
-   Jeśli zamówienie zakupu zostało zaakceptowane i jest widoczne na stronie **Oczekiwanie na akcję odbiorcy**, wynika to z faktu, że nie zostało automatycznie potwierdzone w trakcie akceptacji. Czeka, aż pracownik działu zakupów zmieni mu status na Potwierdzone. Zazwyczaj zamówienie zakupu uważa się za porozumienie między odbiorcą a dostawcą z chwilą zaakceptowania zamówienia przez dostawcę. Przeniesienie zamówienia zakupu do stanu Potwierdzone jest wtedy formalnością.

Po wybraniu zamówienia zakupu pojawiają się dodatkowe informacje o odpowiedzi. Widać szczegóły wierszy i odpowiedzi do każdego wiersza. Stan wiersza pokazuje, której z poniższych odpowiedzi udzielono.

-   Zaakceptowano
-   Odrzucona
-   Zaakceptowano ze zmianami
-   Zastąpiono/Substytut
-   Podziel do harmonogramu/Wiersz harmonogramu

Należy zauważyć, że wskaźnik pokazuje **Dostarczanie**=tak/nie, co informuje, że towary z wierszy nie zostaną dostarczone. Może to wynikać z faktu, że wiersz został odrzucony, lub zastąpiony w sytuacji, gdy towary z oryginalnych wierszy nie miały być dostarczane, albo że towary z wiersza podzielonego na wiele wierszy harmonogramu i towary z oryginalnego wiersza nie miały być dostarczane zgodnie z otrzymanym zamówieniem. Wyświetlane są wszystkie zmiany wprowadzone do odpowiedzi na wiersz zamówienia, z wyjątkiem przekazanych notatek i załączników, które można zobaczyć przy użyciu internetowego interfejsu współpracy z dostawcami.

## <a name="open-confirmed-orders"></a>Otwarte potwierdzone zamówienia
Gdy zamówienie zakupu zostanie potwierdzone przez odbiorcę, tzn. jego stan zostanie zmieniony na Potwierdzone, pojawi się jako otwarte potwierdzone zamówienie. Pozostanie na tej liście do momentu, aż zostanie zarejestrowane jako przyjęte przez odbiorcę.





