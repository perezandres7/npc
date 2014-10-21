npc
===

type
  TCalcular = class(TThread)
    inicio: longint;
    limite: longint;
    LLista: TListBox;
    EResult: TEdit;
    LFinalizado: TLabel;
    PBarra: TProgressBar;

    constructor Create; reintroduce; overload;
    procedure Execute; override;
    function rotar_obt_npc(var num:longint): boolean;
    function existe_numeroListBox (numero: string; lista: TListBox): integer;
  end;

implementation

{$R *.dfm}

constructor TCalcular.Create;
begin
  inherited Create(True);
end;

procedure TCalcular.Execute;
var
  n: longint;
  cont,acum,num,i,j,contbarra: longint;
begin
  inherited;

      cont:= 0;
      for i:= inicio to limite do
      begin
       contbarra:= i;
       num:=i;
       acum:=0;
       for j:= 1 to num do
        if num mod j = 0 then
          acum:= acum + 1;
        if acum = 2 then {significa q es primo, debo averiguar si es npc}
        begin
          n:= num;
          if existe_numeroListBox(IntToStr(n), LLista) = -1 then
          begin
             if rotar_obt_npc(num) then
               begin
                 {cuento y pongo el npc para mostrar}
                 cont:= cont + 1;
                 LLista.Items.Add(IntToStr(num));
                 EResult.Text:= IntToStr(cont);
                 LFinalizado.Caption:='CALCULANDO...';
                 PBarra.Position:= cont;
               end;
          end;
        end;
        {efecto semicompleto}
        PBarra.Position:= cont;
        PBarra.Position:= contbarra;
      end;
      LFinalizado.Caption:='FINALIZADO';
end;

function TCalcular.rotar_obt_npc(var num:longint): boolean;
var
   esnpc:boolean;
   numero,cant,acum,i,j,k:integer;
   ultimo:char;
   cad,cad2: string[6];

begin
        cad:= IntToStr(num);
        cad2:= cad;
        cant:= length(cad);
        esnpc:= true;
        for i:= 1 to cant do
         begin
            ultimo:= cad2[1];
            for j:= 2 to cant do
             begin
              cad2[j-1]:= cad[j];
              cad2[j]:= ultimo;
             end;
            cad:=cad2;
            numero:= StrToInt(cad2);
            acum:=0;
            for k:= 1 to numero do
              if numero mod k = 0 then
                  acum:= acum + 1;
            if acum > 2 then
               esnpc:= false;
         end;
         rotar_obt_npc:= esnpc;
end;

function TCalcular.existe_numeroListBox (numero: string; lista: TListBox): integer;
var
  i: integer;
begin
  existe_numeroListBox:= -1;

  for i := 0 to lista.Count - 1 do
  begin
    if AnsiUpperCase (lista.items[i]) = AnsiUpperCase (numero) then
    begin
      existe_numeroListBox := i;
      Exit;
    end;
  end;
end;

procedure TFormNPC.BitBtnIniciarClick(Sender: TObject);
var
  Calcular,Calcular2: TCalcular;
  Calcular3,Calcular4: TCalcular;
  Calcular5,Calcular6: TCalcular;
  Calcular7,Calcular8: TCalcular;
  Calcular9,Calcular10: TCalcular;
  Calcular11,Calcular12: TCalcular;
  Calcular13,Calcular14: TCalcular;
  Calcular15,Calcular16: TCalcular;
  Calcular17,Calcular18: TCalcular;
  Calcular19,Calcular20: TCalcular;

begin
  BitBtnIniciar.Visible:= False;
  Image1.Visible:= True;

  {1}
  Calcular:= TCalcular.Create(True);
  Calcular.inicio:= 2;
  Calcular.limite:= 50000;
  Calcular.LLista:= ListBoxLista1;
  Calcular.EResult:= EditResult;
  Calcular.LFinalizado:= LabelFinalizado;
  Calcular.PBarra:= ProgressBarBarra;
  Calcular.FreeOnTerminate := True;
  Calcular.Resume;
  
  {2}
  Calcular2:= TCalcular.Create(True);
  Calcular2.inicio:= 50001;
  Calcular2.limite:= 100000;
  Calcular2.LLista:= ListBoxLista2;
  Calcular2.EResult:= EditResult2;
  Calcular2.LFinalizado:= LabelFinalizado2;
  Calcular2.PBarra:= ProgressBarBarra2;
  Calcular2.FreeOnTerminate := True;
  Calcular2.Resume;

  {3}
  Calcular3:= TCalcular.Create(True);
  Calcular3.inicio:= 100001;
  Calcular3.limite:= 150000;
  Calcular3.LLista:= ListBoxLista3;
  Calcular3.EResult:= EditResult3;
  Calcular3.LFinalizado:= LabelFinalizado3;
  Calcular3.PBarra:= ProgressBarBarra3;
  Calcular3.FreeOnTerminate := True;
  Calcular3.Resume;

  {4}
  Calcular4:= TCalcular.Create(True);
  Calcular4.inicio:= 150001;
  Calcular4.limite:= 200000;
  Calcular4.LLista:= ListBoxLista4;
  Calcular4.EResult:= EditResult4;
  Calcular4.LFinalizado:= LabelFinalizado4;
  Calcular4.PBarra:= ProgressBarBarra4;
  Calcular4.FreeOnTerminate := True;
  Calcular4.Resume;

  {5}
  Calcular5:= TCalcular.Create(True);
  Calcular5.inicio:= 200001;
  Calcular5.limite:= 250000;
  Calcular5.LLista:= ListBoxLista5;
  Calcular5.EResult:= EditResult5;
  Calcular5.LFinalizado:= LabelFinalizado5;
  Calcular5.PBarra:= ProgressBarBarra5;
  Calcular5.FreeOnTerminate := True;
  Calcular5.Resume;

  {6}
  Calcular6:= TCalcular.Create(True);
  Calcular6.inicio:= 250001;
  Calcular6.limite:= 300000;
  Calcular6.LLista:= ListBoxLista6;
  Calcular6.EResult:= EditResult6;
  Calcular6.LFinalizado:= LabelFinalizado6;
  Calcular6.PBarra:= ProgressBarBarra6;
  Calcular6.FreeOnTerminate := True;
  Calcular6.Resume;

  {7}
  Calcular7:= TCalcular.Create(True);
  Calcular7.inicio:= 300001;
  Calcular7.limite:= 350000;
  Calcular7.LLista:= ListBoxLista7;
  Calcular7.EResult:= EditResult7;
  Calcular7.LFinalizado:= LabelFinalizado7;
  Calcular7.PBarra:= ProgressBarBarra7;
  Calcular7.FreeOnTerminate := True;
  Calcular7.Resume;

  {8}
  Calcular8:= TCalcular.Create(True);
  Calcular8.inicio:= 350001;
  Calcular8.limite:= 400000;
  Calcular8.LLista:= ListBoxLista8;
  Calcular8.EResult:= EditResult8;
  Calcular8.LFinalizado:= LabelFinalizado8;
  Calcular8.PBarra:= ProgressBarBarra8;
  Calcular8.FreeOnTerminate := True;
  Calcular8.Resume;

  {9}
  Calcular9:= TCalcular.Create(True);
  Calcular9.inicio:= 400001;
  Calcular9.limite:= 450000;
  Calcular9.LLista:= ListBoxLista9;
  Calcular9.EResult:= EditResult9;
  Calcular9.LFinalizado:= LabelFinalizado9;
  Calcular9.PBarra:= ProgressBarBarra9;
  Calcular9.FreeOnTerminate := True;
  Calcular9.Resume;

  {10}
  Calcular10:= TCalcular.Create(True);
  Calcular10.inicio:= 450001;
  Calcular10.limite:= 500000;
  Calcular10.LLista:= ListBoxLista10;
  Calcular10.EResult:= EditResult10;
  Calcular10.LFinalizado:= LabelFinalizado10;
  Calcular10.PBarra:= ProgressBarBarra10;
  Calcular10.FreeOnTerminate := True;
  Calcular10.Resume;

  {11}
  Calcular11:= TCalcular.Create(True);
  Calcular11.inicio:= 500001;
  Calcular11.limite:= 550000;
  Calcular11.LLista:= ListBoxLista11;
  Calcular11.EResult:= EditResult11;
  Calcular11.LFinalizado:= LabelFinalizado11;
  Calcular11.PBarra:= ProgressBarBarra11;
  Calcular11.FreeOnTerminate := True;
  Calcular11.Resume;

  {12}
  Calcular12:= TCalcular.Create(True);
  Calcular12.inicio:= 550001;
  Calcular12.limite:= 600000;
  Calcular12.LLista:= ListBoxLista12;
  Calcular12.EResult:= EditResult12;
  Calcular12.LFinalizado:= LabelFinalizado12;
  Calcular12.PBarra:= ProgressBarBarra12;
  Calcular12.FreeOnTerminate := True;
  Calcular12.Resume;

  {13}
  Calcular13:= TCalcular.Create(True);
  Calcular13.inicio:= 600001;
  Calcular13.limite:= 650000;
  Calcular13.LLista:= ListBoxLista13;
  Calcular13.EResult:= EditResult13;
  Calcular13.LFinalizado:= LabelFinalizado13;
  Calcular13.PBarra:= ProgressBarBarra13;
  Calcular13.FreeOnTerminate := True;
  Calcular13.Resume;

  {14}
  Calcular14:= TCalcular.Create(True);
  Calcular14.inicio:= 650001;
  Calcular14.limite:= 700000;
  Calcular14.LLista:= ListBoxLista14;
  Calcular14.EResult:= EditResult14;
  Calcular14.LFinalizado:= LabelFinalizado14;
  Calcular14.PBarra:= ProgressBarBarra14;
  Calcular14.FreeOnTerminate := True;
  Calcular14.Resume;

  {15}
  Calcular15:= TCalcular.Create(True);
  Calcular15.inicio:= 700001;
  Calcular15.limite:= 750000;
  Calcular15.LLista:= ListBoxLista15;
  Calcular15.EResult:= EditResult15;
  Calcular15.LFinalizado:= LabelFinalizado15;
  Calcular15.PBarra:= ProgressBarBarra15;
  Calcular15.FreeOnTerminate := True;
  Calcular15.Resume;

  {16}
  Calcular16:= TCalcular.Create(True);
  Calcular16.inicio:= 750001;
  Calcular16.limite:= 800000;
  Calcular16.LLista:= ListBoxLista16;
  Calcular16.EResult:= EditResult16;
  Calcular16.LFinalizado:= LabelFinalizado16;
  Calcular16.PBarra:= ProgressBarBarra16;
  Calcular16.FreeOnTerminate := True;
  Calcular16.Resume;

  {17}
  Calcular17:= TCalcular.Create(True);
  Calcular17.inicio:= 800001;
  Calcular17.limite:= 850000;
  Calcular17.LLista:= ListBoxLista17;
  Calcular17.EResult:= EditResult17;
  Calcular17.LFinalizado:= LabelFinalizado17;
  Calcular17.PBarra:= ProgressBarBarra17;
  Calcular17.FreeOnTerminate := True;
  Calcular17.Resume;

  {18}
  Calcular18:= TCalcular.Create(True);
  Calcular18.inicio:= 850001;
  Calcular18.limite:= 900000;
  Calcular18.LLista:= ListBoxLista18;
  Calcular18.EResult:= EditResult18;
  Calcular18.LFinalizado:= LabelFinalizado18;
  Calcular18.PBarra:= ProgressBarBarra18;
  Calcular18.FreeOnTerminate := True;
  Calcular18.Resume;

  {19}
  Calcular19:= TCalcular.Create(True);
  Calcular19.inicio:= 900001;
  Calcular19.limite:= 950000;
  Calcular19.LLista:= ListBoxLista19;
  Calcular19.EResult:= EditResult19;
  Calcular19.LFinalizado:= LabelFinalizado19;
  Calcular19.PBarra:= ProgressBarBarra19;
  Calcular19.FreeOnTerminate := True;
  Calcular19.Resume;

  {20}
  Calcular20:= TCalcular.Create(True);
  Calcular20.inicio:= 950001;
  Calcular20.limite:= 999999;
  Calcular20.LLista:= ListBoxLista20;
  Calcular20.EResult:= EditResult20;
  Calcular20.LFinalizado:= LabelFinalizado20;
  Calcular20.PBarra:= ProgressBarBarra20;
  Calcular20.FreeOnTerminate := True;
  Calcular20.Resume;
end;

end.
