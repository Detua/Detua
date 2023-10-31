program VerificarProgressao;
var
  Termo1, Termo2, Termo3, Razao: real;
  Soma: real;
  i: integer;
  PA, PG: boolean;
begin
  writeln('Informe o primeiro termo: ');
  readln(Termo1);
  writeln('Informe o segundo termo: ');
  readln(Termo2);
  writeln('Informe o terceiro termo: ');
  readln(Termo3);
  { Verificar se é uma PA ou PG }
  if (Termo2 - Termo1 = Termo3 - Termo2) then
    PA := True
  else if (Termo2 / Termo1 = Termo3 / Termo2) then
    PG := True;
  { Calcular a soma dos 10 primeiros termos }
  Soma := 0;
  if PA then
  begin
    Razao := Termo2 - Termo1;
    for i := 1 to 10 do
      Soma := Soma + Termo1 + (i - 1) * Razao;
  end
  else if PG then
  begin
    Razao := Termo2 / Termo1;
    for i := 1 to 10 do
      Soma := Soma + Termo1 * power(Razao, (i - 1));
  end;
  { Exibir resultados }
  if PA then
    writeln('A sequência é uma progressão aritmética.')
  else if PG then
    writeln('A sequência é uma progressão geométrica.');
  writeln('A soma dos 10 primeiros termos é: ', Soma:0:2);
end
