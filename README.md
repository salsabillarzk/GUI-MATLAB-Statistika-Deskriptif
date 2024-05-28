```
function varargout = Statdes(varargin)
% STATDES MATLAB code for Statdes.fig
%      STATDES, by itself, creates a new STATDES or raises the existing
%      singleton*.
%
%      H = STATDES returns the handle to a new STATDES or the handle to
%      the existing singleton*.
%
%      STATDES('CALLBACK',hObject,eventData,handles,...) calls the local
%      function named CALLBACK in STATDES.M with the given input arguments.
%
%      STATDES('Property','Value',...) creates a new STATDES or raises the
%      existing singleton*.  Starting from the left, property value pairs are
%      applied to the GUI before Statdes_OpeningFcn gets called.  An
%      unrecognized property name or invalid value makes property application
%      stop.  All inputs are passed to Statdes_OpeningFcn via varargin.
%
%      *See GUI Options on GUIDE's Tools menu.  Choose "GUI allows only one
%      instance to run (singleton)".
%
% See also: GUIDE, GUIDATA, GUIHANDLES

% Edit the above text to modify the response to help Statdes

% Last Modified by GUIDE v2.5 09-Oct-2022 13:59:40

% Begin initialization code - DO NOT EDIT
gui_Singleton = 1;
gui_State = struct('gui_Name',       mfilename, ...
                   'gui_Singleton',  gui_Singleton, ...
                   'gui_OpeningFcn', @Statdes_OpeningFcn, ...
                   'gui_OutputFcn',  @Statdes_OutputFcn, ...
                   'gui_LayoutFcn',  [] , ...
                   'gui_Callback',   []);
if nargin && ischar(varargin{1})
    gui_State.gui_Callback = str2func(varargin{1});
end

if nargout
    [varargout{1:nargout}] = gui_mainfcn(gui_State, varargin{:});
else
    gui_mainfcn(gui_State, varargin{:});
end
% End initialization code - DO NOT EDIT


% --- Executes just before Statdes is made visible.
function Statdes_OpeningFcn(hObject, eventdata, handles, varargin)
% This function has no output args, see OutputFcn.
% hObject    handle to figure
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
% varargin   command line arguments to Statdes (see VARARGIN)

% Choose default command line output for Statdes
handles.output = hObject;

% Update handles structure
guidata(hObject, handles);

% UIWAIT makes Statdes wait for user response (see UIRESUME)
% uiwait(handles.figure1);


% --- Outputs from this function are returned to the command line.
function varargout = Statdes_OutputFcn(hObject, eventdata, handles) 
% varargout  cell array for returning output args (see VARARGOUT);
% hObject    handle to figure
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Get default command line output from handles structure
varargout{1} = handles.output;
```

```
% --- Executes on button press in pushbutton_tutup.
function pushbutton_tutup_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton_tutup (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
closereq();


% --- Executes on button press in pushbutton_hitung.
function pushbutton_hitung_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton_hitung (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
x=str2num(get(handles.edit_data,'string'));
n=length(x);
Mean=num2str(mean(x));
Median=num2str(median(x));
Modus=num2str(mode(x));
Stdev=num2str(sqrt(var(x)));
Varian=num2str(var(x));
checkboxMean=get(handles.checkbox_mean,'Value');
if(checkboxMean)
    set(handles.edit_mean,'String',Mean);
end
checkboxMedian=get(handles.checkbox_median,'Value');
if(checkboxMedian)
    set(handles.edit_median,'String',Median);
end
checkboxModus=get(handles.checkbox_modus,'Value');
if(checkboxModus)
    set(handles.edit_modus,'String',Modus);
end
checkboxStdev=get(handles.checkbox_stdev,'Value');
if(checkboxStdev)
    set(handles.edit_stdev,'String',Stdev);
end
checkboxVarian=get(handles.checkbox_var,'Value');
if(checkboxVarian)
    set(handles.edit_varian,'String',Varian);
end
axes(handles.axes5)
hist(x)
xlabel('Data')
ylabel('Frekuensi')
grid on
axes(handles.axes6)
boxplot(x)
xlabel('Data')
grid on

% --- Executes on button press in checkbox_mean.
function checkbox_mean_Callback(hObject, eventdata, handles)
% hObject    handle to checkbox_mean (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of checkbox_mean


% --- Executes on button press in checkbox_median.
function checkbox_median_Callback(hObject, eventdata, handles)
% hObject    handle to checkbox_median (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of checkbox_median


% --- Executes on button press in checkbox_modus.
function checkbox_modus_Callback(hObject, eventdata, handles)
% hObject    handle to checkbox_modus (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of checkbox_modus


% --- Executes on button press in checkbox_stdev.
function checkbox_stdev_Callback(hObject, eventdata, handles)
% hObject    handle to checkbox_stdev (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of checkbox_stdev


% --- Executes on button press in checkbox_var.
function checkbox_var_Callback(hObject, eventdata, handles)
% hObject    handle to checkbox_var (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hint: get(hObject,'Value') returns toggle state of checkbox_var


% --- Executes on button press in pushbutton_reset.
function pushbutton_reset_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton_reset (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
set(handles.edit_mean,'string','');
set(handles.edit_mean,'string','');
set(handles.edit_median,'string','');
set(handles.edit_modus,'string','');
set(handles.edit_stdev,'string','');
set(handles.edit_varian,'string','');
set(handles.edit_data,'string','');
set(handles.checkbox_mean,'Value',0);
set(handles.checkbox_median,'Value',0);
set(handles.checkbox_modus,'Value',0);
set(handles.checkbox_stdev,'Value',0);
set(handles.checkbox_var,'Value',0);
set(handles.uitable1,'Data','');

function edit_mean_Callback(hObject, eventdata, handles)
% hObject    handle to edit_mean (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_mean as text
%        str2double(get(hObject,'String')) returns contents of edit_mean as a double


% --- Executes during object creation, after setting all properties.
function edit_mean_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_mean (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end



function edit_median_Callback(hObject, eventdata, handles)
% hObject    handle to edit_median (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_median as text
%        str2double(get(hObject,'String')) returns contents of edit_median as a double


% --- Executes during object creation, after setting all properties.
function edit_median_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_median (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end



function edit_modus_Callback(hObject, eventdata, handles)
% hObject    handle to edit_modus (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_modus as text
%        str2double(get(hObject,'String')) returns contents of edit_modus as a double


% --- Executes during object creation, after setting all properties.
function edit_modus_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_modus (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end



function edit_stdev_Callback(hObject, eventdata, handles)
% hObject    handle to edit_stdev (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_stdev as text
%        str2double(get(hObject,'String')) returns contents of edit_stdev as a double


% --- Executes during object creation, after setting all properties.
function edit_stdev_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_stdev (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end



function edit_varian_Callback(hObject, eventdata, handles)
% hObject    handle to edit_varian (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_varian as text
%        str2double(get(hObject,'String')) returns contents of edit_varian as a double


% --- Executes during object creation, after setting all properties.
function edit_varian_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_varian (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end



function edit_data_Callback(hObject, eventdata, handles)
% hObject    handle to edit_data (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)

% Hints: get(hObject,'String') returns contents of edit_data as text
%        str2double(get(hObject,'String')) returns contents of edit_data as a double


% --- Executes during object creation, after setting all properties.
function edit_data_CreateFcn(hObject, eventdata, handles)
% hObject    handle to edit_data (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    empty - handles not created until after all CreateFcns called

% Hint: edit controls usually have a white background on Windows.
%       See ISPC and COMPUTER.
if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor'))
    set(hObject,'BackgroundColor','white');
end


% --- Executes on button press in pushbutton_updata.
function pushbutton_updata_Callback(hObject, eventdata, handles)
% hObject    handle to pushbutton_updata (see GCBO)
% eventdata  reserved - to be defined in a future version of MATLAB
% handles    structure with handles and user data (see GUIDATA)
handles.filename=uigetfile('*.xlsx');
guidata(hObject,handles);
filename=handles.filename;
datax=xlsread(filename);
x=datax(:,1);
set(handles.edit_data,'String',x)
set(handles.uitable1,'Data',x)
```
